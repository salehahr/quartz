---
title: Sockets Errno 10054
date: "2020-07-20"
external_url: "http://docs.microsoft.com/en-gb/windows/win32/winsock/windows-sockets-error-codes-2?redirectedfrom=MSDN"
tags:
  - software/sockets
  - -sa/processed
---

Parent: [SofaPython Index](sofapython-index.md)

WSAECONNRESET
10054
Connection reset by peer.
An existing connection was forcibly closed by the remote host. This normally results if the peer application on the remote host is suddenly stopped, the host is rebooted, the host or remote network interface is disabled, or the remote host uses a hard close (see setsockopt for more information on the SO\_LINGER option on the remote socket). This error may also result if a connection was broken due to keep-alive activity detecting a failure while one or more operations are in progress. Operations that were in progress fail with WSAENETRESET. Subsequent operations fail with WSAECONNRESET.

