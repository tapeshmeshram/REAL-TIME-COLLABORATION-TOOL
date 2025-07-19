#REAL-TIME-COLLABORATION-TOOL
Company Name: CODTECH IT SOLUTIONS PVT. LTD.
Intern Name: Tapesh Meshram
Intern ID: CT04DG2441
Domain: Software Development
Batch Duration: June 20, 2025 - July 20, 2025
Mentor Name: Neela Santhosh Kumar

For this task, I built a real-time collaboration server using Express and Socket.IO. The goal was to allow multiple users to edit the same document at the same time, similar to tools like Google Docs. This is done by using WebSocket communication, where changes made by one user are instantly sent to all other users connected to the same document.

The backend uses Node.js with the http and socket.io libraries. When a user connects, they emit a join-document event along with a document ID. The server then joins them to a socket room specific to that document. If the document already exists, its current content is loaded and sent back to the user. When any user makes an edit, they emit an edit-document event, and the server broadcasts this new content to everyone else in the same room using socket.to(docId).emit().

The content is stored in memory using a simple JavaScript object. In a real-world scenario, this would be connected to a database to persist document data. The server also listens for the disconnect event to track when users leave.

I configured CORS to allow communication with a frontend running on localhost:3000, assuming React or a similar framework is used on the client side. Though this task focuses only on the backend, it can be tested easily with a simple HTML + JavaScript client or with a more advanced frontend.

This task helped me understand how real-time communication works using WebSockets. I learned how to manage rooms, synchronize shared data across multiple users, and handle events in a real-time environment. It also showed me the importance of performance and low latency when dealing with collaborative tools.

The server runs on port 4000 and is structured in a clean, scalable way. It can easily be expanded to support authentication, persistent storage, or multiple document types.
