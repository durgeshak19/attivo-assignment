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
4. All the necessary dependencies will be installed by running the above scripts.
Port 3000 : webSocketServer
Port 5000 : server
Port 8081 : mongoserver

### Design write up
a. Used Web sockets to connect server to several Clients. Created Another web server to serve the requests from client and update the mongo database.

Seperating servers achieve

1. Easy to Scale : as an ordinary server have over 60000 sockets therfore it can be an equally large no of clients can served. To reach even more a Load balancer could be put in place to distribute traffic and scale up.
2. Reduces Complexity and easy to maintain : Seaprating business logic helps maitaining and modifying of either of the servers and can be run on separate machines without breaking the other.
3. Relatively Inexpensive server to run websockets and specialized expensive to update database reduces overall cost.

b. Used MongoDB database as there is no relation between data and storing into mongo collections is easier as client sends JSON data , which directly can be saved into a NoSql database.

c. Used Docker to make a shippable product as asked. In application Docker also used to solve MongoDB connection and configuration problems as encountered during development.

d. Used Express js as a backend framework for faster application development.

### Working

1. webSocketServer.js creates a websocket it logs whenever a new cient is connected. A timer (interval 1 minutes) has been setup to ping all the connected clients and requests their data.
2. when client gets a ping request it logs the current number of requests and call the functions to serve OS details to server.
 ##### Caching
  A caching mechanism checks if there is any error on sending the requests and       loops every minutes until particular request is served. 
  To acheive a true Cache a STACK could be used to save unserviced requests and     when connections is re-established pop the stored requests.
3. Client intitiates POST request to server on different URLs for the server to    catch .
4. Routing Server then stores the requested data and stores into database based on their types.


### Technical Difficulties faced 
1. Connecting large no of clients cant be done using simple Client-server architecture. So learned fundamentals of Websockets from Scratch and implemented it.
2. Running mongo client in local machine constantly failing to establish connection on ports and on Atlas Cloud.
3. Used Dockers to make a shippable product as asked in the assignment therefore again learning from scratch. 


### Brownie Points Acheived
1. Can be run into Windows and Linux as used technologies [Node js ,docker] readily runnable on both systems.
2. Can be easily scaled up to 1000+ machines as using websockets permits so. Any host running the Client program can easily connects to the server websocket and then send data on another after every n minutes. Using two servers offloads traffic and further the use of load balancer can also redistribute the Load. 


### Libraries/Framework Used 
Websocket 
Express 
Axios 
MongoDB
ps-list
node-disk-info
