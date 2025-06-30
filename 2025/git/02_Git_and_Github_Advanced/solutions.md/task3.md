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

- Stash the changes

                  command : git stash 

it saves the changes without commiting them .

- Switch to another branch and apply the stash.

                    command: git checkout master 
                             git stash pop



# git stash apply VS git stash pop 

- git stash apply : It applies the stash changes to your working directory and keeps the stash in the stash list ( to reuse again).

- git stash pop: It applies the stash changes to working directory but removes the stash from the stash list after applying .