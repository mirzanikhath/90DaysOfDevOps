# SHELL SCRIPTING 

shell scripting in linux involves writing a sequence of commands in a text file, which the shell then interprets and executes , automating the tasks and simplifying repetitive operations.

some key concepts of shell scripting are :

1. shell script: shell script is a file that runs the unix command by command line interpreter.
2. purpose : shell scripts are used to automate tasks , execute commands and manage files and processes.
3. shell: common shell include bash (bourne again shell),zsh and others.
4. basic structure of shell script:
   - shebang: the first line of the shell script #!/bin/bash , this specifies the interpreter to be used .
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

part 1:- shell script  for creating the user will look like :


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

    
part 2:- shell script for deleting the user :



   #!/bin/bash

   #script to delete user accounts with options and validation

   #function to delete user 
   delete_user() {
      read -p "Enter the username to delete :" usernamer

      #check if user exists 
      if id "$username" &>/dev/null; then 
          sudo userdel -r "$username"
          if [$? -eq 0]; then 
             echo "user '$username' has been successfully deleted."
          else
             echo "failed to delete user '$username'."
          fi 
      else 
         echo " user '$username' does not exist."
         exit 1 
      fi 
   }
   
   

The above script is used to delete the username if exits and removes user and the home directory where -d and --delete are required for deletion  of the user after deletion it gives us back the successful message of deletion .

Part-3:- shell script for password reset of the user 


#!/bin/bash 

#script to reset the password for the existing user 

read -p "Enter the username:" username 

#check if the user exists 

if id "$username" $>/dev/null; then 
    read -s -p "Enter the new password:" password 
    echo 
    read -s -p "Confirm the new password:" password_confirm 
    echo

    #check if passwords match 
    if [ "$password" != "$password_confirm"]; then 
        echo "passwords do not match. try again."
        exit 1 

    fi
     # set a new password 
     echo "$username:$password"| sudo chpasswd 

     # confirm success 
     if [$? -eq 0]; then 
        echo "password reset successfully for the user '$username'."

     else 
        echo " failed to reset the password for the user '$username'."

     fi 
else 
   echo " user '$username' does not exists."
   exit 1
fi 

The above shell script first check whether the user is present and resets the password and confirms it after confirmation it resets the password accordingly . Then at last it prints the username and latest password changed .




    
