# Java-Based-Real-Time-Chat-Application

This is a chat application written in Java. The application consists of a server that manages multiple client connections and a client that connects to the server to participate in the chat room.

## Features

- **Server**: Handles multiple clients concurrently using threading.
- **Client**: Connects to the server and allows the user to send and receive messages.
- **Nickname**: Clients can set a nickname upon connection and change it during the session.
- **Broadcast**: Messages from one client are broadcast to all connected clients.
- **Commands**:
  - `/nick <new_nickname>`: Change your nickname.
  - `/quit`: Disconnect from the chat room.

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or higher.

### Running the Server

1. Compile the `Server.java` file:

   ```sh
   javac Server.java
2. Run the server:
   ```sh
   java Server
  The server will start and listen for client connections on port 9999.

### Running the Client
1. Open two terminal shells for clients.
2. Compile the `Client.java` file:
   
   ```sh
   javac Client.java
3. Run the client:

   ```sh
   java Client
   
  The client will attempt to connect to the server running on 127.0.0.1 (localhost) on port 9999.

4. Start chatting! Type messages to send them to the chat room. All messages will be broadcast to all connected clients.

5. Use `/nick <new_nickname>` to change your nickname.

6. Use `/quit` to disconnect from the chat room.
   
### Usage
- Upon starting, the client will prompt the user to enter a nickname.
- Type messages to send them to the chat room. All messages will be broadcast to all connected clients.
- Use `/nick <new_nickname>` to change your nickname.
- Use `/quit` to disconnect from the chat room.

### Server
The server is implemented in the `Server` class. It uses a `ServerSocket` to listen for client connections and a thread pool to handle multiple clients concurrently.

- **ConnectionHandler**: Inner class that handles communication with a single client.
- **broadcast(String message)**: Sends a message to all connected clients.
- **shutdown()**: Shuts down the server and closes all client connections.

### Client
The client is implemented in the `Client` class. It connects to the server using a `Socket` and starts an `InputHandler` thread to handle user input from the console.

- **InputHandler**: Inner class that reads user input from the console and sends it to the server.
- **shutdown()**: Shuts down the client and closes the connection to the server.
