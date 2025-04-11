# PROCESS MANAGEMENT AND MONITORING 

In linux process management involves monitoring , controlling and optimizing running programs and services. Essential tools like ps, top, and htop provide insights into active processes, while commands like kill and nice allow you to control and prioritize them.effective process management ensures system stability , enhance overall performance and prevents resource exhaustion . 

process management is the key source for linux users, as the processes are the programms running on our system .

What Are Processes in Linux?

a process in linux is the instance of running programm or service . processes can be system processes (background processes) or the user processes ( an application started by a user).

Key Concepts of Linux Processes:

1. process identifier(PID): a unique identifier assinged to every process. 
2. parent and child processes: processes that create other processes in the form of heriarchy.
3. foreground and background : processes can run interactively (foreground) and in the background .
4. states of processes: processes can be running, sleeping , stopped or zombie.

How to View Processes in Linux:

1. ps command : 
* this command helps to view all the processes which are actively running .
                
                command : ps aux

    - a: shows processes from all users.
    - u: display user-oriented information.
    - x: includes processes without terminal .

2. top command :
* this command displays real time information about the processes.
                  
                  command : top

    - press q to quit .
    - press h to help.

3. htop command :
* an interactive and user-freindly alternative to top command .

                 command : htop

    - use arrow key to navigate .
    - press f9 to kill the process.

4. pgrep command : 
* it finds the processes by their names 

            command : pgrep firefox


How to Control Processes in Linux

1. starting the process :

              command : firefox &

    - & command helps to run the process in background .

2. bringing background processes to foreground.:

               command: fg %1

    - fg command it to bring the processes to foreground .

3. pausing and resuming processes:

    - pause the process 

               command : kill -STOP (PID)

    - resume the process

               command : kill -CONT (PID)

4.  killing the processes. 

              command : kill -9 (PID)

    - -9 helps to kill the process recursively .

    