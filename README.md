# project-erlang
# CPLT - Actor-based Concurrency Module

## Erlang Lab Class #3 - Project

----
To submit your answers, simply push your files onto the repository. The problem will be graded.

----

## Messaging system
Messaging systems, such as WhatsApp and Discord, are widely used. 
In this project the goal is to implement a simple messaging system.


### Overview 

* **Register**
  * Users can register in the system with a given nickname.
  * Only registered users can connect to the server.
* **Connect**
  * A registered user can connect to the server.
  * Once a user is connected to the server they can join any number of chat rooms.
  * After registration it is assumed that the user is connected.
* **Join a chat room**
  * Chat rooms are identified by an string that starts with #, e.g., #christmas.
  * When a user joins a chat room that does not exist, a new chat room is created. 
* **Write a post**
  * After joining a chat room, users can write posts in that chat room.
* **Leave a chat room**
  * User can leave a chat room.
  * In order to disconnected, a user must leave all the chat rooms previously joined.
* **Disconnect**
  * Disconnects from the server
    
### System Components
* The system has two components: 
  * The client that sends the requests to the server; and 
  * The server that manages the client's requests.
*The server can include multiple processes.
* Based on the projected description define the interaction protocol between client and server.

### Supported Requests
The client interacts with the server with the following requests:
* **register** in the messaging server given a nickname:
  * Server possible replies: *ok*, *already_registered*
* **connect** to the messaging server
  * Server possible replies: ok, already_connected, unknown_user
* **disconnect** from the messaging server
  * Server possible replies: ok, still_in_chatroom, not_connected
* **join** a chat room
  * Server possible replies: ok, already_joined
* **write** a message in a chat room
  * Server possible replies: ok, not_joined
* **leave** a chat room
  * Server possible replies: ok, not_joined

### Requirements
* Create also client processes such that the number of these client processes to be created should be received as a parameter.
* In the **project report** explain your solution and what properties your implementation ensures, justifying your claims.
