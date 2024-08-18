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

### Byte Order Conversion
Byte order is the order in which the sequential bytes are stored in a hex number. There are 2 types of byte orders: Little Endian and Big Endian. Consider a 4 byte number, `0xdeadb33f`. In Big Endian, it is stored as the four sequential bytes in this order, `de`, `ad`, `b3`, `3f`. In Little Endian, it is stored in the opposite order, `3f`, `b3`, `ad`, `de`, i.e., the little end is stored first. 

The Network Byte order is always Big Endian, i.e., the network transmissions always happen with data stored in that order.
The host byte order in most systems is Little Endian.

When doing network data transmission, we must convert the data we input into network byte order from host byte order. We can convert 4 bytes (or short), and 8 bytes (or long).
There are functions to do that: `h` for host, `to` for to, `n` for network, `s` for short and `l` for long.

| Function  | Description           |
| --------- | --------------------- |
| `htons()` | host to network short |
| `htonl()` | host to network long  |
| `ntohs()` | network to host short |
| `ntohl()` | network to host long  |


