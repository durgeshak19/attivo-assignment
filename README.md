# Attivo Networks Assignment


## Task
To design a client-server architecture in which a server sends multiple "types of requests" to large no. of clients , and client service those requests by responding back to the server.These server requests are to be made periodically "to each client every" n minutes.

## How to run Scripts

### Prerequisites installed
1. Docker 
2. Node js

### To run Scripts
1. Create a clone of the repository in a folder using " git clone git@github.com:durgeshak19/attivo-assignment.git ".  
2. Go to the attivo-server directory in terminal and run bash file using ./run-server.sh. This will start Mongo server [in docker] ,routing server and websocket server in your system.
3. Similarly got to attivo-client directory and run ./run-client.sh . This will start client side socket and connections will be established between the server and client.

### Design write up
a. Used Web sockets to connect server to several Clients. Created Another web server to serve the requests from client and update the mongo database.

Seperating servers achieve

1. Easy to Scale : as an ordinary server have over 60000 sockets therfore it can be an equally large no of clients can served. To reach even more a Load balancer could be put in place to distribute traffic and scale up.
2. Reduces Complexity and easy to maintain : Seaprating business logic helps maitaining and modifying of either of the servers and can be run on separate machines without breaking the other.
3. Relatively Inexpensive server to run websockets and specialized expensive to update database reduces overall cost.

b.
### Technical Difficulties faced 
1. Connecting large no of clients cant be done using simple Client-server architecture. So learned fundamentals of Websockets from Scratch and implemented it.
2. Running mongo client in local machine constantly failing to establish connection on ports.
3. Used Dockers to make a shippable product as asked in the assignment therefore again learning from scratch. 
