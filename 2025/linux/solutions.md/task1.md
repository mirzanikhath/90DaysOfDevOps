# Week 2: Linux System Administration & Automation

linux is the most popular operating system among windows and MacOs . this operating system helps in automation , gives high security and is flexible for deployment of applications .
linux is the kernel based operating system where kernel is called as heart of linux distribution.linux is an open source operating system which is derived from UNIX .
linux operating system was first created by linus torvarld as an open source which can be used free of cost .
linux has a single kernel with multiple distributions . linux is like clone of unix but not unix as unix has multiple kernel versions but linux has single kernel . 

LINUX ARCHITECTURE:

Linux architecture mainly consists of 3 main layers 
1-Hardware : the physical component of the machine like memory(RAM) and processesor (CPU).
2-Kernel : the heart of linux operating system which works as communication between hardware and processes.
3-Processes : Kernel-controlled running programs on the system. Processes make up all tasks outside the kernel.

The kernel plays very important role in linux operating system . There are some main components of kernel 
Bootloader: it is the programm which runs everytime when the linux system power ups or restarts . the main primary use of bootloader is it boots the process in linux operating system from starting . 
The most commonly used bootloaders are GRUB (GRand Unified Bootloader) and LILO (LInuxs LOader).

LINUX KERNEL 

Kernel is the lowest level of operating system . Kernel is like a communication between the hardware and the applications.The linux kernel is monolithic. 

Linux kernel helps in following components :
1 - device drivers : kernel always acts as communication between the hardware and processes.
2 - memory: kernel keeps track of memory usage like what is stored and where .
3 - process management: Schedules CPU requests from processes and distributes the processor time accordingly.
4 - System calls and security: The kernel handles all system calls and processes the requests in the kernel space.

# LINUX USER GROUPS 

linux user groups are digital clubs which maintains which member can have permission to the system and change the system this should be used very carefully that who should have acces to our linux system .

the linux user groups are like bunch of members who has access or permission to the file and system equally . they are like team working on a particular project who has permissions 

there are mainly two user groups in linux :
1- primary group
2- secondary group 

Here's an example for the user group named nikhath which is created by using the command:
        [ command :sudo useradd --create-home nikhath ]

Linux automatically makes a primary group also called "nikhath". You can check this in the /etc/passwd file:
        [ command : grep nikhath /etc/passwd]

There are some more user groups which built-in and custom groups 
built-in groups : the groups which are ready made already present in the system like 'root','users','sudo'.

custom groups : the groups which can ne made for our own needs example "projects" groups which can be made by the user for his own need .

Good group management is the key to keep the linux system secure and run smoothily.
The reason Linux so elegantly supports a multi-user system is as a result of permissions. Permissions grant users the right to access files and directories within the system.


Making new group

1. for creating a group we need permission of root user so we use sudo command:

          [command: sudo groupadd new_group_name]

2. to check if the group is added :

          [command: sudo cat etc/group]

3. To add a user to a group:

          [command: sudo usermod -aG  group_name user_name ]

4. the -a in the above command is most important as it add the user to a group without removing it from other group.

          [example: sudo usermod -aG developer nikhath]

Changing Group Settings

1. Change a user's main group:

       [command:sudo usermod -g new_primary_group username]

2. Add a user to multiple groups:

      [command:sudo usermod -aG group1,group2,group3 username]

3. Change a group's ID:

      [command:sudo groupmod -g new_gid group_name]
      
          
Deleting Groups and Users:

1. To remove a user from a group:

      [command:sudo gpasswd -d username group_name]

2. To delete a group:

       [command:sudo groupdel group_name]

3.  To delete a user:   

       [command:sudo userdel username]

Q1. Create a user devops_user and add them to a group devops_team.

ans : created a user devops_user by using command: sudo useradd devops_user
      created a group devops_team by using command : sudo usermod -aG devops_team devops_user

Q2. Set a password and grant sudo access.
ans : password set by using command :      sudo passwd devops_user
      granted sudo acces by using command: sudo usermod -aG sudo devops_user
      to very the sudo access or switching the sudo user  command :su - devops_user

Q3. Restrict SSH login for certain users in /etc/ssh/sshd_config
ans : Open the SSH Configuration File command: sudo vim /etc/ssh/ssh_config
      Add the DenyUsers line   command : DenyUsers user1 user2 user3 
      Restart the SSH Service command : sudo systemctl restart .ssh
      we can also deny access to groups by using command: DenyGroups group_name


