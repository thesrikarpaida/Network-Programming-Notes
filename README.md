# Network-Programming-Notes
This repo is my notes taken when referring to Beej's Network Programming Guide.

It is recommended to have a basic knowledge of C programming and basic computer networking concepts before referring to these notes.

### What is a socket?
In terms of network programming, a socket is a file descriptor for network communication.
You can call it a socket descriptor. It can be considered as another file descriptor, just like anything else in the Unix environment, and it is used for sending and receiving data through a network connection.
The socket descriptor can be obtained by `socket()` function and the data communication happens through using functions like `send()` and `recv()`.

### Types of Sockets
There are many different types of sockets, but the most popular ones are stream sockets and datagram sockets. They are connection-oriented and connectionless respectively. Basically, associate them to TCP and UDP.
Stream sockets (TCP) - `SOCK_STREAM`
Datagram Sockets (UDP) - `SOCK_DGRAM`
