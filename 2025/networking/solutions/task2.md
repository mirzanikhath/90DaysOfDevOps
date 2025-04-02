# PROTOCOLS AND PORTS FOR DEVOPS 

PORT:-
port is like a virtual gateway that a service,application or process on our computer uses for network communication.
each port is assigned different port numbers which allows different network traffic to be directed to appropriate network.

there are 3 different port ranges :
1- well-known/system port : the well-known or system port is most commonly used reserved ports used by the system services. these are mostly used for default application, the port like HTTP(80),HTTPS(443),SMTP(25),SSH(22).
 
2- registered ports :-these ports are assigned to the application or system services which are less common .

3- dynamic/private ports: these ports are short lived and are used temporarily for a small application to test whether it works properly or not .

# TCP/UDP PROTOCOLS 

tcp/udp are two different protocols which uses ports for data transmission.The main difference in these two is how they manages work and transmits the data differently .for example, in tcp the data transmitted is registered and confirmed message we recieve after the data is transmitted ,while in udp there is no registered data to be transmitted nor we get a confirmed message .

TCP PROTOCOL :

tcp (transmission control protocol ) is a connection based protocol . it ensure the connection before sending or recieving the data from the any service,tcp protocol most reliable protocol as it ensure the data transmitted is happened without any delay and in correct order . examples of tcp protocol are  emails ,file transfer ,etc...

UDP PROTOCOL:

udp (user datagram protocol) is a connectionless protocol . it transmits the data fast without checking the connection and the order of sending the data whether it is sent in a perfect order or not . the main focus of udp protocol is to ensure the data should be sent on time and fast as soon as possible ,this udp protocol is widely used while gaming, streaming as the user does not requires any lag in that .

# EXAMPLES OF COMMON PROTOCOLS UTILIZING TCP AND UDP 

* the most common protocols used by tcp are: 

- HTTP/HTTPS (80,443) used for web browsing 
- FTP (21) used for tranferring file 
- SMTP(25) used for transferring emails 
- SSH(22) secure shell used for secure remote administration of devices 

* the most common protocols used by udp are: 
- DNS(53) domain name system used for domain name resolution 
- DHCP(67) dynamic host configuration protocol issuing IP addresses.
- NTP (123) network time protocol 
- VoIP(56) voice over internet protocol used for phone conversations 

While most networks rely on numerous ports, the most common ports used in a networking environment:

- Port 80 – HTTP (Hypertext Transfer Protocol)
- Port 443 – HTTPS (HTTP Secure)
- Port 22 – SSH (Secure Shell)
- Port 21 – FTP (File Transfer Protocol)
- Port 25 – SMTP (Simple Mail Transfer Protocol)
- Port 53 – DNS (Domain Name System)
- Port 110 – POP3 (Post Office Protocol version 3)
- Port 143 – IMAP (Internet Message Access Protocol)
- Port 3389 – RDP (Remote Desktop Protocol)
- Port 23 – Telnet
