# Task 3: Stashing - Save Work Without Committing

# Stashing :

Git stash command temporarily saves your uncommited changes (in working directory and staging area) so that we can work on something else.

Your working directory becomes clean, as if you hadn't made any changes . You can later reapply those changes when you're ready.

# Usage:

- You're working on something , but need to quickly switch branches. 
- You're not ready to commit changes yet . 

Scenario: You need to switch branches but don’t want to commit incomplete work.

- Modify a file without committing.
                  
                  command : echo "Temporary Change" >> temp.txt
                            git add temp.txt
![Screenshot 2025-06-30 145701](https://github.com/user-attachments/assets/1ef25744-c234-4342-8e0e-f858458572e1)



- Stash the changes

                  command : git stash 

it saves the changes without commiting them .

- Switch to another branch and apply the stash.

                    command: git checkout master 
                             git stash pop


![Screenshot 2025-06-30 145721](https://github.com/user-attachments/assets/9f1fa8a7-3178-4b64-a2cf-dfd93b1db13d)

- When I run git stash pop command it applied the changes saved in my most recent stash and then removed the stash from the stash list . 
- After popping the stash , I now have temp.txt staged for commit in my stashed work, so it's back in staging. 
- The last line confirms the stash was removed . 

# git stash apply VS git stash pop 

- git stash apply : It applies the stash changes to your working directory and keeps the stash in the stash list ( to reuse again).

- git stash pop: It applies the stash changes to working directory but removes the stash from the stash list after applying .
