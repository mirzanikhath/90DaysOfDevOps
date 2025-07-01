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

- Resolve conflicts  if any and continue.
 
                    command : git rebase --continue 

As you can see in above documentation i faced a conflict with a file data/general.json , to resolve that conflict I used vim editor to edit that file and removed the unwanted lines and then run the command git rebase --continue and given the new commit message and finally rebased the master branch onto feature branch .           