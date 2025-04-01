# Week 1:networking challenge
Networking in DevOps play an important and crucial role for automation,deployment and testing processes.
1.Infrastructure design : infrastructure design in devOps is the core concept of networking where the DevOps engineers implements the infrastructure that supports developmentands deployment . This includes setting up the networks,routers and firewall services to run the infrastructure smoothly .This design also helps in building protocols which helps in deployment and make the infrastructue scalable.

2Applicationdeployment:   engineers uses networking in the deployment of application to the production environment.the networking concepts and tools helps in running the application smoothly.The network related issues can be solved with the help of networking at the time of applicationdeployment.

3.Automation: DevOps is based on automating the processes by using the networking tools . the most famous tools that helps in automation are terraform and ansible which configures and maintains the data to be automated .

4.Monitorinng: DevOps engineers uses the networking concept to monitor the work and infrastructure and solving the issues related to network and trouble-shooting the networking protocols issues during the development and deployment .

# task:1 :- understanding  OSI & TCP/IP models  

OSI MODELS:
-> the OSI(open system interconnection )plays a very important and vital role in the world of DevOps where different system are coonnected under the same network and works together.
This OSI model is a framework of the transmitted networks between different systems . It consists of 7 layers 
1- physical layer
2- data link layer
3- network layer
4- transport layer
5- session layer
6- presentation layer
7- application layer

# PHYSICAL LAYER :
The lowest layer of OSI model is called as physical layer . This layer is responsible for connection between the devices . The informiation stored in the physical layer is in the form of bits (binary digits). the network is tranfered through this physical with the help of hubs,cables,modems,etc..which the transfer the  network to data link layer . 

 function of physical layer 
1 - synchronization : the physical layer provides the bits to run at the same time with the help of clock wise system . this clocks notes both sender and reciever bits at the same time .

2- bit rate control: physical layer also defines and records number of bits transmitted per second 

3- physical topologies : physical layer also specifies different nodes or devices connected or arranged in a network 

4- transmission mode: physical layer defines breifly that how the network flows between two connected devices .

# DATA LINK LAYER:
Data link layer is the important layer of osi model which help in delivery of messages from one node to another node. Data link layer transmits the data from node to node in the physical layer. 
It transmits the message from production to host with the help of MAC address or IP address . the devices that helps in data link layer are switches and bridges.

there are two sublayers of data link layer:
1- logical link control (LLC)
2- media link control (MAC)

 FUNCTION OF DATA LINK LAYER 
1- framing: the framing in data link layer helps to transmit the data from sender to reciever in a particular bits pattern in the starting and ending of the frames.

2- physical addressing : the data link layer proivides the address to each frames.

3- error control:the data link layer provides a mechanism in which it detects the error like retransmit of damage .

4- flow control: the data link layer controls the flow of data from sender to reciever by the proper acknowledgment .

5- access control:when a communication channel is shared among different devices the data link layer  controls which devices has the access at the partiucular time .

# NETWORK LAYER :
network layer in osi models tramnsmits the data from one device to another device that are working on different networks .network layer usually work on routing that is selecting the smallest path to transmit the data from one device to another . it uses the help of IP addresses in order to locate the devices which are working in different layers . the devices used under the metwork layer are routers and switches .

 functions of network layer

1- routing : the routing in network layer is done for finding which route is suitable for the transmission of data from sender to reciever . It also helps in identifying which route easily transmits the data and select that route .
2- logical adderessing :the network layer works on the protocol that providing the IP addresses to the devices so that it can easily identify the senders and recievers during the transmission and flow of data can be done easily 

# TRANSPORT LAYER :

transport layer in osi model provides the service to the application layer and takes service from network layer . the data under the transport layer is called as segment , it is responsible for end-to-end transport of complete message. ttransport layer also provides the acknowledgment of the complete transmission of data and retransmits the data if any error is found .

the protocols used under the transport layer are TCP,UDP etc..

# SESSION LAYER  
session layer in osi model helps in establishment of connections, management of connections, and termination of session between two devices . these are done by using protocols .

 functions of session layer 

1- dialog control :dialog control in session layer manages the flow of data between two devices , determining which transmits first and when and ensuring the data transfer is organised and prevent conflicts .

2- synchronization : the synchronization in session layer ensures the same data is being transmitted between two devices or not . and if not it resynchronize the transmission .

# PRESENTATION LAYER 

presentation layer is also called as translation layer which transmits the data as per required to the application layer and extracts the data as per required format . 

functions of presentation layer 

1- translation
2- encryption/decryption
3- compression

# APPLICATION LAYER 

application layer is the top layer of osi model which connects user experiences to software applications and allows the user to access data and network services . 

functions of application layer 

1- file transfer : the file transfer protocol is supported by application which transfers the file securely from local to remote 

2- mail services : the application layer provides the email services securely 

3- directory service : the application layer provides the distributed databases and global collects the information about various objects and services .

# TCP/IP MODEL

The TCP/IP stands for transmission control protocol/internet protocol is suite of communication protocols used to interconnect network devices on the internet.

TCP/IP is used for communication protocol in a private computer network .

TCP/IP model consists of 4 layers
1- application layer 
2- transport layer 
3- internet layer 
4- network access layer  

The package delivery in TCP/IP model is not guaranteed , it is widely used in actual networks like internet and communication system 