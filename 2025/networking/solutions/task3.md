# AWS EC2 AND SECURITY GROUPS 

step 1-: go  to aws console login
step 2-: click on launch instance 
step 3-: type an instance name 
step 4-: select the user as ubuntu 
step 5-: select your instance type  
step 6-: click on create a new key pair
step 7-: give the name of the key pair and create it 
step 8-: allow HTTP and SSH traffic

# SECURITY GROUPS 

security groups are like virtual firewalls which gives inbound and outbound traffic for a cloud insatnce like ec2 instance on AWS . these security groups dictates which access is to be given or denied based on their IP adderesses ,ports and protocols .

security groups give the instance level security which means it gives the security only to the instances .
the inbound (incoming) and outbound (outgoing ) traffic is being controlled by the security groups .the security
group are statefullness as they depending on the inbound rule controls the outbound traffic traffic of that particular port .

security groups prevents the unauthorized access to cloud instance  protecting the sensitive data inside our  cloud instance .security groups simplify our network management by allowing to manage the security of multiple instances in the single configuration.

RULES 

1- defining traffic 
  - protocols : TCP,UDP,ICMP
  - ports : port range is must 
  - source / destination: the ip addresses of source and destination is required .

2- inbound rules : the inbound rules controls the incomming traffic to the instance 
3- outbound rule : the outbount rules controls the outgoing traffic of the instance 

SIGNIFICANCE OF SECURITY GROUPS 

1- enhanced security 
2- granular control 
3- simplified management 

