# Real-Time Chat Application

This is a simple real-time chat application implemented in C++ using WinSock for network communication. It includes both server and client components, enabling multiple clients to connect to the server and communicate with each other.

## Features

- Real-time message broadcasting to all connected clients.
- Multithreading to handle multiple clients simultaneously.
- Simple and easy-to-understand code structure.

## Requirements

- Windows operating system.
- Visual Studio or any other C++ compiler that supports WinSock.
- WinSock2 library.

## Getting Started

### Prerequisites

Make sure you have WinSock2 library installed on your system. This library is typically included with most Windows development environments.

### Building the Application

1. Clone the repository:
    ```sh
    git clone https://github.com/GeeteshMehto/Real-Time-Chat-Application.git
    cd realtime-chat-app
    ```

2. Open the project in Visual Studio (or any other C++ development environment).

3. Build the project. This will compile both the server and client applications.

### Running the Server

1. Run the server executable. The server will start listening for client connections on port `12345`.
    ```sh
    ./server.exe
    ```

2. The server will output messages indicating its status, such as "server has started listening on port: 12345".

### Running the Client

1. Run the client executable. The client will attempt to connect to the server running on `127.0.0.1` (localhost) on port `12345`.
    ```sh
    ./client.exe
    ```

2. Enter your chat name and start sending messages.

## Code Overview

### Server Code

The server code initializes WinSock, creates a listening socket, and waits for client connections. For each client connection, it spawns a new thread to handle communication with that client.

- **Initialization**: The `Initialize()` function initializes WinSock.
- **InteractWithClient()**: Handles communication with a connected client. It receives messages from the client and broadcasts them to all other connected clients.
- **Main Function**: Sets up the server socket, binds it to an address and port, and starts listening for connections. It accepts new clients and creates a new thread for each one.

### Client Code

The client code initializes WinSock, creates a socket, and connects to the server. It uses two threads: one for sending messages and one for receiving messages.

- **Initialization**: The `Initialize()` function initializes WinSock.
- **SendMsg()**: Handles user input and sends messages to the server.
- **ReceiveMsg()**: Receives messages from the server and displays them.
- **Main Function**: Sets up the client socket, connects to the server, and starts the send and receive threads.

## Example Usage

1. Start the server:
    ```sh
    ./server.exe
    ```

2. Start multiple clients in separate terminal windows:
    ```sh
    ./client.exe
    ```

3. Enter your chat name and start chatting!

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- This project uses WinSock for network communication.
- Special thanks to the C++ community for their helpful resources and tutorials.

