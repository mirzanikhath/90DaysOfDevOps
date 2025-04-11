# SHELL SCRIPTING 

shell scripting in linux involves writing a sequence of commands in a text file, which the shell then interprets and executes , automating the tasks and simplifying repetitive operations.

some key concepts of shell scripting are :

1. shell script: shell script is a file that runs the unix command by command line interpreter.
2. purpose : shell scripts are used to automate tasks , execute commands and manage files and processes.
3. shell: common shell include bash (bourne again shell),zsh and others.
4. basic structure of shell script:
   - shebang: the first line of the shell script !/bin/bash , this specifies the interpreter to be used .
   - commands : the commands written in shell script should each command on a new line .
   - variables : we can define the variables in the shell scripts .
   - control flow: Scripts can use if, else, for, while statements to control execution flow. 
   - functions : we can write functions inside the shell scripts which are to be called .

Examples : 

1. creating a shell script for listing all the files :

           !/bin/bash
           ls -l

2. creating a shell script for changes the name of the file :

            !/bin/bash 
            mv old_file.txt new_file.txt

Execution:

1. to make the script executable: 

           command : chmod +x script_name.sh

2. to run the script file: 

             command : ./script_name.sh 


Advantages of shell scripting:

- Automation: use to automate the repetitive task and simplify the work flow .
- efficiency: save time and efforts by executing multiple commands in the single script.
- portability: shell scripts are platform independent we can easily move them in the linux system . 

# USER ACCOUNT MANAGEMENT :

In Linux, user account management is done by using following commands useradd,usermod,userdel,passwd,groupadd and groupdel.Scripts can be created to automate tasks such as creating new user, changing user attributes , deleting accounts and managing groups.

Breakdown of common tasks and how they can be achieved in shell scripts:

1. Creating a New User: for creating a new user use useradd with neccesary options . and set their default shell as /bin/bash.

                   command: sudo useradd -d /home/newuser -s /bin/bash/newuser

2. set a password for newuser: use passwd for setting a password for the user.

                   command : sudo passwd newuser

3. Modifying User Attributes: changing the home directory of the user  extinguser use usermod .

                  command : sudo usermod -d  /home/new_home extinguser 

4. Deleting a User: for deleting the olduser use userdel command .

                 command : sudo userdel -r olduser 

5. create a new group : to add new group use groupadd 

                command : sudo groupadd developer

6. delete the group : to delete the group we use groupdel 

                 command : sudo groupdel developer 

7. add user to group : to add user to group we use usermod with -aG to avoid making changes in the existing  membership. 

                command : sudo usermod -aG developer newuser

as you have seen above to run these all commands we need alot of time to execute them one by one shell scripts helps us to use these all commands as text in the scripts file and run them altogether.

shell script  for creating the user will look like :


     #!/bin/bash
     #script to create a new user
     username= "nikhath"
     password= "mirza1234"

     if [ -z "$username" ] || [ -z "$password" ]; then
       echo "Usage: $0 <username> <password>"
       exit 1
    fi

    # create a new user 
    sudo useradd -d /home/"$username" -s /bin/bash "$username"

    #set password 
    echo "$username:$password" | sudo chpasswd

    #set home directory permission
    sudo chmod -R 750 /home/"$username"

    #set the home directory ownership 
    sudo chown -R "$username":/home/"$username"

    echo 'user "$username" is succesfully created'.

    


    
