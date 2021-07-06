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

### Solution
Used Web sockets to connect server to several Clients. Created Another web server to serve the requests from client and updata the mongo database.

Seperating servers achieve

1. Easy to Scale as an ordinary server have over 60000 sockets therfore it can be  
