# Multithreaded-chat-application

**COMPANY**: CODTECH IT SOLUTIONS

**NAME**: B.AKHILMITRA

**INTERNID**: CT12GPD

**DOMAIN**: JAVA

**BATCH DURATION**: DECEMBER 25TH,2024 TO FEBRUARY 25TH,2025

**MENTOR NAME**: NEELA SANTHOSH KUMAR

# ENTER DESCRIPTION OF TASK PERFORMED NOT LESS THAN 500 WORDS

A **multithreaded chat application** allows multiple users to communicate in real-time, with each client being handled independently through separate threads. The application consists of two main components: the **server** and the **client**.

### **Server Side:**
The server listens for incoming client connections on a specific port. When a client connects, the server spawns a new thread to handle communication with that particular client. This allows the server to handle multiple clients simultaneously without blocking. The server maintains a collection of active client connections and broadcasts any message received from one client to all others, ensuring real-time communication.

- The server uses a `ServerSocket` to listen for incoming client connections.
- Each connection is handled by a new thread (`ClientHandler`), which reads messages from the client and sends them to all connected clients.
- The server ensures that the messages are broadcasted to all clients using a synchronized collection (`clientWriters`), which contains `PrintWriter` objects that write data to each client.

### **Client Side:**
The client connects to the server and allows the user to send and receive messages. The client interface runs in two separate threads:
1. **Message Sending Thread**: The main thread allows the user to type messages, which are sent to the server.
2. **Message Receiving Thread**: A separate thread listens for incoming messages from the server and displays them on the client’s console.

- Clients can send messages by typing into the console.
- Incoming messages are displayed as they are received from the server.
- Clients can type "exit" to disconnect from the server.

### **Key Features:**
1. **Multithreading**: Each client connection is handled by a separate thread, allowing the server to serve multiple clients concurrently.
2. **Real-time Messaging**: Messages from one client are immediately broadcasted to all other connected clients.
3. **Simple Communication Model**: The server uses a straightforward broadcast approach to send messages to all clients, making it easy to implement and understand.
4. **Scalability**: Although designed for basic usage, this structure can be extended for more advanced features like private messaging, message history, or even file transfer.

### **Application Flow**:
- The client connects to the server.
- The server accepts multiple clients and spawns threads for each.
- Clients send messages, which are broadcasted to others in real-time.
- Clients can disconnect by typing "exit".

### **Conclusion**:
This chat application demonstrates a fundamental multithreaded communication model where multiple users can chat in real time. It handles basic messaging features and can be extended to include more complex features. The use of threads ensures that the server can support many clients without blocking, while each client has a responsive interface for sending and receiving messages.
