# Task 2: Undoing Changes – Reset & Revert
# Git reset :
- Moves the current branch pointer (HEAD) to different commit. 
- Can change the staging area and even your working directory . 

Types:
 - --soft : moves HEAD only -> changes stay staged 
 - --mixed : Moves HEAd and resets staging -> changes remain unstaged . 
 - --hard : Moves HEAD, resets staging and wipes chnages from working directory -> dangerous as changes are lost. 

 we use git reset when we want to rewrite history locally or unstage changes .

 # Git revert :
 - Create a new commit that undoes changes from a specific earlier commit . 
 - Safe for shared history -> doesn't remove commits but adds a "reverse" one.
 - Example : git revert <comit-hash>

 We use git revert when we have to undo changes but keep a clean, visible history .

 Scenario: You accidentally committed incorrect changes and need to undo them.

 - Create and modify a file.
                    
                    command : echo "wrong code" >> wrong.txt

This command creates and prints wrong code in that new file . 
To add this file 

                  command : git add . 

to commit changes :

                 command : git commit -m " commited by mistake "
![Screenshot 2025-06-30 142818](https://github.com/user-attachments/assets/e5e5e4bf-451f-43f0-8cf2-ab0cf7c27ff0)

- Soft Reset (keeps changes staged).

                command : git reset --soft HEAD~1

- Mixed Reset (unstages changes but keeps files).

                command : git reset --mixed HEAD~1

- Hard Reset (removes all changes).

                command : git reset --hard HEAD~1
![Screenshot 2025-06-30 143033](https://github.com/user-attachments/assets/0fe5f550-0f84-48df-a2a8-478548b4aa95)

- Revert a commit safely.
                
                command : git revert HEAD
![Screenshot 2025-06-30 143301](https://github.com/user-attachments/assets/9d362186-526c-4cbf-a381-5558dbae8019)

  

                
