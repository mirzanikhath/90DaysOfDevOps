# HANDS -ON NETWORKING COMMANDS 

There are several networking commands in linux operating system which are the essential toolkit for the network administrator and system administrator .These commands performs complex networking tasks like monitoring , troubleshooting , and network configuration .

# COMMANDS :

1- man : the man command gives the manual page of the commands there usage and information 
       syntax : man [command]

2- ip : The ip command helps view and configure routing, interfaces, network devices, and tunnels.
       syntax: ip [options] objects [command]

3- ifconfig: ifconfig command shows the network interface information on the system .this command is from the package of net-tools 
       syntax: ifconfig [option] [command]

4- dig: The dig command queries Domain Name Systems (DNS) and finds information for DNS records. The command collects domain name information and associated records.
       syntax: dig [options] [domain] [record type] [DNS server]

5- nslookup: nslookup command is similar to dig command . the main difference in both commands is the nslookup command features the interactive mode.
       syntax: nslookup [domain] [DNS server]

6- netstat: netstat command shows the networking statistics utility.it also shows the availability of ports.
       syntax: netstat [options]
    
7-  traceroute: traceroute command traces the route of the network which it takes to reach the destination of TCP/IP .
       syntax: traceroute [options] [hostname/IP]

8- host:The host command is a simple tool for performing DNS lookups.
       syntax: host [options] [hostname/IP]

9- ping: The ping command is a network utility for testing whether a host is reachable. 
       syntax: ping [options] [hostname/IP]

10- route: The route command in Linux is a specialized command for displaying and configuring the routing table.
       syntax: route [options] [subcommand] [arguments]

11- curl or wget: The wget and curl commands are command-line tools for downloading files from the internet. The two tools are similar, but there are slight differences in how they work and the options they offer:

*The wget command downloads files from the web using HTTP, HTTPS, or FTP protocols. The tool is simple to use for file downloads.

*The curl command is versatile and supports various network protocols, such as SCP, IMAP POP3, SMTP, etc. The tool also sends HTTP requests and interacts with web services.
        syntax: wget [options] [URL]
        syntax: curl [options] [URL]
        