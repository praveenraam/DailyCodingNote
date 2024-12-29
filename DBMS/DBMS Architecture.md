Topic No : 2
Previous Topic : 
Next Topic :

### What is Architecture
DBMS Architecture helps users to get their requests done while connecting to the database

### Client and Server

- **Client** : Client here we mention is none but the user himself.
- **Server** : Server is the place where the request is processed and response is sent.

### Types of Architecture

#### 1 Tier Architectures

**In this tier, the user can access the database without any layer in between them.** Using the database in the local device. This is mostly used for local level development.

**Example** : to learn SQL we set up an SQL server and the database on the local system.
![[Pasted image 20241229171911.png]]
#### 2 Tier Architectures

**In this tier, there are two layers, One is Client layer and another is server layer.** 
Here the Application (GUI) on the client side send request with the database. The server side respond to the request.

- To communicate in the 2 tier we need to make a connection with the server.

**Example** : Booking a railway ticket in Station.
![[Pasted image 20241229171638.png]]

#### 3 tier Architecture

**In this tier the client layer can't direct communicate the database, there is a layer in between them called Application Server.** 

Whenever the client make a request using client application, it is sent to the server application which further process the request in the Database and send the response to the application.

- End user won't have the knowledge about the existence of the Database and vice versa for database.

**Examples** : Amazon app and website, Facebook app and websites.
Here the app and website is the Client application which send the request.
![[Pasted image 20241229172920.png]]

### Difference between 2 and 3 tier application

| 2 Tier Database Architecture             | 3 Tier Database Architecture                |
| ---------------------------------------- | ------------------------------------------- |
| It is Client and server Architecture     | It is web based Architecture                |
| Easy to build and maintain               | Complex to build and maintain               |
| Slower                                   | Faster                                      |
| Less secure                              | Highly secure                               |
| When user increase, performance decrease | System runs on internet, better performance |

