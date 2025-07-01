# Task 5: Rebasing - Keeping a Clean Commit History

# Rebasing : 

Rebasing in Git is a way to move or "replay " a series of commits from one branch to another base commit. 
We use Rebase command as it makes history cleaner and avoinds unnecessary merge commits.Keeps the linear history makes git log easier.Integrate latest changes and keeps your feature branch upto date. 

Rebase takes your changes and replays them on top of a new base commit, helping you keep a neat , linear project history . 

# Difference between merge and Rebase :

- git merge : It combines two branches and preserves full history with merge commits . It results in branching, tree-like structure . It creates merge commits and is safe for shared branches.It resolve conflicts only once at the merge point . Its used when we have to preserve full commit history . 

- git rebase : It moves branch commits to new base. Rewrites the history to be linear . It results in a straight , linear history.It doesnot create merge commits but re-applies commits without merge commit. Its not safe for shared branches . May need to resolve conflicts in multiple commits . Its used when a clean , linear history is desired . 

Scenario: Your branch is behind the main branch and needs to be updated without extra merge commits.

- Fetch the latest changes.
                  
                  command : git fetch origin master 

- Rebase the feature branch onto main.

                   command : git rebase origin/master

![Screenshot 2025-07-01 131110](https://github.com/user-attachments/assets/d82341b0-fc63-4944-8627-eae3b049d842)

- Resolve conflicts  if any and continue.
 
                    command : git rebase --continue 
![Screenshot 2025-07-01 131647](https://github.com/user-attachments/assets/6564bbf9-33d7-4832-9836-246598925042)


As you can see in above documentation i faced a conflict with a file data/general.json , to resolve that conflict I used vim editor to edit that file and removed the unwanted lines and then run the command git rebase --continue and given the new commit message and finally rebased the master branch onto feature branch .           

# Best practices of Rebasing : 

Rebasing is powerful, but it can also cause a mess if used carelessly. The best practices to keep git history clean and avoid trouble .

- Never Rebase Public Branches: Don't rebase commits that other people might have pulled . Only rebase your own local work . 

- Use Rebase to Clean Local Commits : Rebasing is perfect for cleaning up messy commits on your local feature branch , squashing multiple small commits into one logical commit , putiing your work on top of the latest changes from master . 

- Resolve Conflicts Carefully : During rebase check conflicted files , remove conflict markers (<<<<,=========,>>>>) , test your code before continuing , use git add and git rebase --continue command . Don't while resolvng conflicts . 

- Prefer interactive Rebase for Clean History : Interactive rebase lets you squash commits and edit commit messages and drop unnecessary commits. 

- Abort if Things Go Wrong :If the rebase feels messy or confusing abort it this will restore your branch to how it was before you started . 

- Make Backups Before Big Rebases: If We're unsure about the commits by creating backups we can easily recover if our rebase goes wrong . 

- Check Your History Before Pushing : After rebasing we should check our git log to confirm that our commits look correct . 

- Force Push Carefully After Rebase : After rebasing a branch whic is already pushed to remote we will need to run git push --force-with-lease because it checks if the remote branch has changed unexpectedly. 

- Communicate with Team : If we're collaborating on a branch and want to rebase then we need to communicate with our team indicating them that we are rebasing and asking them to wait for push or pull until we are done . 

