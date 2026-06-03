# Multithreaded HTTP Proxy Server

A high-performance multithreaded HTTP proxy server built in C using POSIX sockets, pthreads, semaphores, and an LRU cache. The project demonstrates core systems programming concepts including networking, concurrency control, synchronization, and caching.

## Features

- Multithreaded request handling using POSIX threads
- HTTP request parsing and forwarding
- Thread-safe LRU cache implementation
- Concurrent client connection support
- Synchronization using mutexes and semaphores
- Linux socket programming and system calls

## System Architecture

```text
Client
   |
   v
+-------------------+
| HTTP Proxy Server |
+-------------------+
   |            |
   |            +----> Cache Lookup (LRU)
   |
   v
Origin Server
```

### Request Flow

1. Client sends an HTTP request to the proxy server.
2. Proxy checks whether the requested resource exists in the cache.
3. On a cache hit, the cached response is returned directly.
4. On a cache miss, the request is forwarded to the origin server.
5. The received response is stored in the cache and returned to the client.
6. Multiple clients are served concurrently using threads.

---

## Concepts Implemented

### Networking

- POSIX Socket Programming
- TCP/IP Communication
- Client-Server Architecture
- HTTP Request Handling

### Concurrency

- POSIX Threads (pthreads)
- Thread Synchronization
- Critical Section Protection
- Concurrent Client Processing

### Operating Systems

- Semaphores
- Mutex Locks
- Memory Management
- Inter-Thread Coordination

### Caching

- Least Recently Used (LRU) Cache
- Cache Insertion and Eviction Policies
- Reduced Server Load
- Faster Response Retrieval

---

## Tech Stack

- C
- POSIX Sockets
- Pthreads
- Semaphores
- Linux System Calls

---

## Building and Running

### Clone Repository

```bash
git clone <repository-url>
cd Multithreaded-HTTP-Proxy-Server
```

### Build

```bash
make
```

### Run

```bash
./proxy <port_number>
```

Example:

```bash
./proxy 8080
```

Open:

```text
http://localhost:8080/http://example.com
```

---

## Challenges Addressed

- Managing multiple client connections concurrently
- Preventing race conditions during cache access
- Designing an efficient LRU cache replacement policy
- Synchronizing shared resources using mutexes and semaphores
- Handling network communication reliably using sockets

---

## Future Improvements

- HTTPS and TLS support
- HTTP/2 and HTTP/3 support
- Reverse proxy functionality
- Multiprocessing architecture
- Performance benchmarking and monitoring
- Configurable cache size and eviction policies

---

## Learning Outcomes

This project provided hands-on experience with:

- Linux systems programming
- Computer networking fundamentals
- Concurrency and synchronization
- Socket programming
- Cache design and optimization
- Multithreaded server architecture

---

## License

This project is intended for educational and learning purposes.
