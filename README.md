# Chat-Room Application

This is a simple multi-client chat-room application implemented in Python using socket programming and multi-threading. The application allows multiple clients to connect to a server and exchange messages in real-time.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup and Installation](#setup-and-installation)
- [Running the Server](#running-the-server)
- [Running the Client](#running-the-client)
- [How It Works](#how-it-works)
- [Troubleshooting](#troubleshooting)

## Overview
This chat-room application consists of two main components:
1. **Server (`server.py`)**: Manages the connections and communication between multiple clients.
2. **Client (`client.py`)**: Allows users to connect to the server, choose a nickname, and participate in the chat-room.

## Features
- Real-time messaging between multiple clients.
- Broadcast messages to all connected clients.
- Clients are notified when a new user joins or leaves the chat-room.

## Requirements
- Python 3.x
- Basic understanding of Python and socket programming
- Basic knowledge of multithreading

## Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rishi-vakharia/chat-room-app.git
   ```

2. **Navigate to the project directory:**
   ```bash
   cd chat-room-app
   ```

3. **Ensure Python is installed on your machine:**
   - You can download Python from [python.org](https://www.python.org/downloads/).

## Running the Server

1. **Navigate to the directory containing `server.py`.**

2. **Run the server:**
   ```bash
   python3 server.py
   ```

3. **Output:**
   - The server will start and begin listening for client connections on `127.0.0.1:8080`.
   - Example output:
     ```
     Server is listening on port 8080...
     ```

## Running the Client

1. **Navigate to the directory containing `client.py`.**

2. **Run the client:**
   ```bash
   python3 client.py
   ```

3. **Choose a nickname when prompted.**

4. **Start chatting:**
   - After connecting, you can send messages to the chat-room.
   - Example interaction:
     ```
     Choose a nickname: Alice
     Connected to the server!
     Bob: Hi Alice!
     Alice: Hello Bob!
     ```

## How It Works
- **Server:**
  - The server listens for incoming connections on `127.0.0.1:8080`.
  - When a client connects, the server asks for the client's nickname and adds it to a list of connected clients.
  - Messages received from any client are broadcast to all other connected clients.
  - The server uses threads to handle multiple clients simultaneously. Each client connection runs on its own thread, allowing the server to manage multiple clients without blocking. This ensures that each client can send and receive messages independently.

- **Client:**
  - The client connects to the server, sends its nickname, and starts receiving and sending messages.
  - The client also uses threads to manage two main tasks: listening for incoming messages from the server and sending messages to the server. These tasks run on separate threads (`receive_thread` and `write_thread`), allowing the client to continuously listen and send messages without interruptions.

## Troubleshooting

- **Socket Errors:** Ensure that the IP address and port are correctly configured and that no other service is using the same port.
- **Connection Refused:** Make sure the server is running before starting the client.
- **General Issues:** Restart both the server and client if you encounter unexpected behavior.

## References

https://www.youtube.com/watch?v=3UOyky9sEQY

https://www.neuralnine.com/tcp-chat-in-python/