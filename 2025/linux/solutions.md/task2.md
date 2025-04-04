# FILE PERMISSIONS 

linux file permissions are the backbone  of the linux operating system . which gives who can access,change or runs the files and folders.every linux system has three set of permissions 

1- owner:the person who created the file.
2- groups : the users who are inside that group .
3- others: all the members who are on the system .

Now, there are three categories for each permission:

1- read(r): they acn just read or see the file or folder .
2- write (w): they can modify or change the content in the file or folder.
3- execute(x): they can run the file as a programm or open a folder.

permissions in linux are showed in two ways : letters(symbolic) and numbers(numeric)

letters :the permisson is as [rwxr-xr-x] which means :
1- [rwx]: permission for owners 
2- [r-x]: permission for groups 
3- [r-x]: permission for others

Numbers use these values:
1- 4 (read)
2- 2 (write)
3- 1 (execute)

now if we combine them it will be like :
1- 7(4+2+1)=read,write and execute.
2- 6(4+2)=read and write 
3- 5(4+1)= read and execute

so the munber for [rwxr-xr-x] is 755.
therefore, linux file permissions are the most powerful tools for the security of system files and directories .

SETTING UP FILE PERMISSIONS

1. chmod: Your Permission-Changing Buddy:
  chmod is the command you'll use to change file permissions. It works two ways: symbolic and numeric.

           example:[chmod u+x script.sh](symbolic way)
           example:[chmod 755 script.sh](numeric way)

2. chown: Changing File Ownership:
  chown changes who owns a file.

           syntax:[chown new_owner:new_group filename]
           example:[sudo chown john:developers important_file.txt]

3. chgrp: Just for Changing Groups:
  chgrp is like chown, but it only changes the group:

          syntax:[chgrp new_group filename]
          example:[sudo chgrp marketing project_files/]

when we have to change the file permissions for bunch of files we do it recursively by using -R with each command .

        example:[sudo chmod -R 755 group_name]

Q1. Create /devops_workspace and a file project_notes.txt.
ans : to create a workspace or directory 
             
             command : mkdir /devops_workspace 
      to create a file
      
             command : touch project_notes.txt

Q2. Set permissions:Owner can edit, group can read, others have no access.
ans : the file permission command will be : 

             sudo chmod 640 project_notes.txt

Q3. Use ls -l to verify permissions.
ans : to verify the permissions

             command : ls -l /devops_workspace

