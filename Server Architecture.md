![server architecture.png](https://bitbucket.org/repo/A9ekGz/images/3764532903-server%20architecture.png)

### Legend: ###

**[Grey box]** 

RobocupPlugin: This is the master object of the plugin that creates all the other objects. It is the only object that has access to the gazebo world model. It will call the update functions of its member objects and also update the gazebo world model accordingly

**[Arrows]**

Arrows with square ends indicate that the object it is pointing to is a non-pointer member variable.

Arrows with round ends indicate that the object it is pointing to is a pointer member variable.

Arrows with dashed lines indicate a pointer to another object's method.

**[Block with dashed lines]** Gazebo world object: This is an external object that the plugin has a pointer to.

**[Colored blocks with solid lines: Each of these are an object that exists as members of the RobocupPlugin]**

GameState: This object keeps track of the state of the game and rule violations and an update method to do that. It has two important member objects: Agents and Teams. 

Perceptor: This object fills in the Agent Percept container with the update method. It also is responsible for sending a s-expression string to the server using the send method.

Effector: This object parses any s-expression sent by the server using the onconnect callback. It is reponsible for updating Agent Action container via its update method and keep track of which agent id is associated with socket id.

Server: The server manages connections from the client. When it receives data on a tcp socket, it calls the onconnect method in the Effector object. When the Perceptor finishes updating, it calls the send method and the server sends the data back to the client through the socket.

Agent Action/Percept: These are simply container classes for various perception and effector information. They do not have any methods. Each Agent object has an agent action and agent percept object
