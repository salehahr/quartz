---
title: Sending data using sockets
date: "2020-07-17"
tags:
  - software/python
  - software/sockets
  - -sa/processed
---

**Parent**: [SofaPython Index](sofapython-index.md)

<http://github.com/psomers3/PyDataSocket>

<http://docs.python.org/3/howto/sockets.html>
Sockets: form of IPC (inter-process communication), for cross-platform communication
(Alternatives, for fast IPC: pipes, shared memory)

*   “client” socket - an endpoint of a conversation
    *   e.g. browser, other client applications
*   “server” socket, which is more like a switchboard operator. The client application (your browser, for example) uses
    *   e.g. web server (uses both server and client sockets)

Roughly, how a socket works (ex: clicking a link on the browser)
Client socket (browser) / Receive

*   Creation of a streaming socket s
*   Socket connects to web server on port 80 (normal http port)
*   Connect completes
*   Socket s is used to request the text
*   A reply is sent
*   The socket reads the reply, is destroyed

Server socket (web server) / Send

*   Create a streaming socket
*   Socket is bound to a public host and a well-known port
    *   public host: socket.gethostname()
    *   So that the socket is visible to the outside world
    *   e.g. if s.bind(('localhost', 80)), this is still a server socket, but only visible within the machine
*   Socket listens (on the defined port) to x connections before refusing outside connections

Main loop

*   Server socket accepts connections from outside
*   A server socket doesn't actually send any data nor does it receive any; it just produces client sockets
    *   Each cs created in response to another "c"s doing a connect to the host

Ports

*   low number port are usually reserved (e.g. HTTP, etc)
*   to use an unreserved port, try a high number (4 digits)

