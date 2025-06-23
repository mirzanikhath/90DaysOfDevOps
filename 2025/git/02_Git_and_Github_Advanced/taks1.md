# Task 1: Working with Pull Requests (PRs)

# Pull request :
A pull request is a way to propose changes you've made in a branch to be merged into another branch, usually the main branch of a project.

In simple terms the pull request means you make changes -> push them to GitHub-> you open a pull request -> others can review the changes -> if approved, it gets merged into the main branch. 

Why its called a "pull" request?

Because you're asking the repository owner (or team) to pull the chnages into their branch . 

Example: 
- you create a new branch called feature-login.
- you add login functionality and commit the code .
- you push the feature-login to GitHub.
- you open a pull request to merge feature-login into main .
- your team members review the PRs , give feedback or approve it .
- once, approved its merged into the main branch or codebase.

# Benefits of PRs:
- Enables code reviews .
- Keeps main branch clean and stable.
- Allows for discussion and collaboration .
- Tracks changes , comments and approvals .

1- Fork a repository and clone it locally :



              command : git clone https://github.com/mirzanikhath/fairfield-programming.github.io.git

              command: cd fairfield-programming.github.io



2- Create a feature branch and make changes .

              command : git checkout -b feature-branch
                       
created a new file feature.txt and append a line into it 

             command : echo "New Feature" >> feature.txt

to add this file 

              command : git add .

to commit the chnages 

             command : git commit -m "added new feature"

             