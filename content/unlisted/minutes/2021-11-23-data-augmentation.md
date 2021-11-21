# Data Augmentation

![](/unlisted/minutes/data-aug-skel.png)

![](/unlisted/minutes/data-aug-node-pos.png)

![](/unlisted/minutes/data-aug-degrees.png)

![](/unlisted/minutes/data-aug-node-types.png)


Probably caused by the rotation transformation:  
Rotation of an integer matrix results in floats between 0 and 1.
![](debug-rotate-integer-matrix.png)
**Tried**: rounding to the nearest integer after the rotation, but results (as shown above) not satisfactory.
**Possible solution**: try a coordinate transformation of the node positions instead.