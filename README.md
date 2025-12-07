# Distributed Instant Messaging System (C++ · gRPC · ASIO · Qt · MySQL/Redis)

## Overview
This project is a distributed instant messaging system implemented in C++, featuring a Qt-based desktop client and a multi-service backend architecture. It integrates gRPC, asynchronous TCP networking with ASIO, Redis/MySQL storage, and a modular design inspired by industry-grade messaging systems.

The implementation is based on an open-source teaching project, with significant extensions, restructuring, and refactoring performed to improve architecture clarity, performance, and code quality.

## Core Features
- **Distributed microservice architecture**
  - Gateway service (HTTP + gRPC entrypoint)
  - Authentication/verification service
  - Chat service (TCP long connections, message routing)
  - Status service (online/offline presence)

- **High-performance networking**
  - ASIO-based asynchronous TCP client & server
  - Persistent long connections with heartbeat detection
  - JSON-based TLV message framing to prevent sticky packets
  - Thread-pool powered io_context for scalable networking

- **Qt Desktop Client**
  - Modern chat UI with bubble dialogs
  - Searchable friend list, contacts, chat history
  - Non-blocking network interactions and smooth UI updates

- **gRPC Communication**
  - Service-to-service RPC for authentication, status sync, and routing
  - Load-balanced RPC calls with reconnection & timeout handling

- **Database & Cache Layer**
  - MySQL for persistent storage (users, friends, messages)
  - Redis for caching login states and temporary verification codes
  - Connection pooling to ensure safe concurrent access

