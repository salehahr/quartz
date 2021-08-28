---
title: DefOptimizer::DefPoseOptimization
date: "2020-10-22"
tags:
  - -sa/processed
  - discussion/2020/2020-10
  - SLAM/algos/DefSLAM
---

Parent: [DefTracking::Track](deftracking__track.md)

As far as I understand it:

*   Uses g2o library for the optimisation (graph-based SLAM)
*   cost function terms are converted to edges and nodes
*   each cost function term seems to correspond to an edge in the graph
*   in g2o paper/tutorial: [an edge is fully characterised by its error function and its information matrix](http://www.evernote.com/shard/s484/nl/217355218/ed9e53f1-76f2-48bd-a0c1-3b59ebf0326c)

int DefPoseOptimization(Frame \*pFrame, Map \*mMap, double RegLap, double RegInex,
  double RegTemp, uint NeighboursLayers)
// define optimiser, set solver
optimizer = new ...
optimizer.setSolver(...)

// create node for current frame (value = camera pose Tcw)
vSE3->setEstimate(Converter::toSE3Quat(pFrame\->mTcw));
vSE3->setId(0);
optimizer.addVertex(vSE3);

// add mesh points to graph (as nodes)
setMeshNodes(optimizer, mMap);

// set MapPoint (feature) vertices
const int N = pFrame\->N; // how many features in the current frame
vpEdgesMono.reserve(N);
vnIndexEdgeMono.reserve(N);

// iterate over each feature map point in the current frame (camera observation)
![unknown_filename.3.png](./_resources/DefOptimizer__DefPoseOptimization.resources/unknown_filename.3.png)
{
 MapPoint \*pMP = pFrame\->mvpMapPoints\[i\];

 // observation: 2x1 matrix (2D image point), x and y coords
 cv::KeyPoint &kpUn = pFrame\->mvKeysUn\[i\];
 Eigen::Matrix<double, 2, 1> obs << kpUn.pt.x, kpUn.pt.y;

 // define edge (defined by error function and info. matrix)
 \*e = new g2o::EdgeNodesCamera();

 // get the 3 nodes of the facet, in which the mappoint/feature is embedded
 std::set<Node \*> NodesMp =
  static\_cast<DefMapPoint \*>(pMP)->getFacet()->getNodes();
 e->resize(NodesMp.size() + 1);

 // set 0-th vertex of edge
 e->setVertex(0, dynamic\_cast<g2o::OptimizableGraph::Vertex \*>(
 optimizer.vertex(0)));

 // iterate over NodesMp (each node is 'it')
 {
 e->setVertex(ui, dynamic\_cast<g2o::OptimizableGraph::Vertex \*>(
 optimizer.vertex((\*it)->getIndex())));
 ViewedNodes.insert(\*it);
 }

 // now e has 4 vertices
 // set 2D observation associated with the edge
 e->setMeasurement(obs);
 // set information vector of the edge, Huber
 e->setInformation(Eigen::Matrix2d::Identity() \* invSigma2 / N);
 e->setRobustKernel(rk);

 // compute error (between observation/meas and projected point?)
 e->fx = pFrame\->fx;
 ... // camera parameters (from calibration matrix)
 e->computeError();

 optimizer.addEdge(e);
}

// temporal smoothness ![unknown_filename.1.png](./_resources/DefOptimizer__DefPoseOptimization.resources/unknown_filename.1.png)
// iterate over all viewednodes (roughly num. features x 3 facet nodes?)
{
 OptLap \= ViewedNodes;

 \*e = new g2o::EdgesReference();
 e->setVertex(0, dynamic\_cast<g2o::OptimizableGraph::Vertex \*>(
 optimizer.vertex((\*it)->getIndex())));

 e->setMeasurement(v) // v from initial pose of viewednodes
 e->setInformation(...)
 optimizer.addEdge(e);
 e->computeError();

 // add neighbouring nodes to OptLap
}

// Laplacian regulariser ![unknown_filename.png](./_resources/DefOptimizer__DefPoseOptimization.resources/unknown_filename.png)
{
 // iterate over OptLap
 ...
 e->setMeasurement(InitialMeanCurvature);
 e->setInformation(RegLap \* Eigen::Vector1D::Identity() / OptLap.size());
 optimizer.addEdge(e);
}

// Inextensibility ![unknown_filename.2.png](./_resources/DefOptimizer__DefPoseOptimization.resources/unknown_filename.2.png)
{
 // iterate over medges (derived from OptLap) 
 s << (\*ite)->getDist();
 e->setMeasurement(s);
 e->setInformation(RegInex \* Eigen::Vector1D::Identity() / medges.size());
 e->computeError();
 optimizer.addEdge(e);
}

optimizer.optimize(50);

// Reprojection error? ![unknown_filename.3.png](./_resources/DefOptimizer__DefPoseOptimization.resources/unknown_filename.3.png)
{
 // Iterate over vpEdgesMono
 \*e = vpEdgesMono\[i\];
 ...
 e->computeError();
 auto a = e->errorData();
 double er = sqrt(pow(a\[0\], 2) + pow(a\[1\], 2));
 sumError += er;

 cout << "Reprojection error: " << sumError / n << endl;
}

// new vertex that seems to return the pose from optimiser
vSE3\_recov = static\_cast<g2o::VertexSE3Expmap \*>(optimizer.vertex(0));
SE3quat\_recov = vSE3\_recov->estimate();
pose = Converter::toCvMat(SE3quat\_recov);

