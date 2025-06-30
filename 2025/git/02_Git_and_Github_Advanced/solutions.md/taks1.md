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
![Screenshot 2025-06-23 152700](https://github.com/user-attachments/assets/a12a34cf-093a-44db-80b4-5355e03cc220)
![Screenshot 2025-06-23 152811](https://github.com/user-attachments/assets/53daa707-7d60-4908-90ac-052c0eb8cb97)


              command : git clone https://github.com/mirzanikhath/fairfield-programming.github.io.git

              command: cd fairfield-programming.github.io
![Screenshot 2025-06-23 153007](https://github.com/user-attachments/assets/daa9f746-bfff-4d2c-89d7-0fae340fab3f)
![Screenshot 2025-06-23 153145](https://github.com/user-attachments/assets/0bed8b4d-018f-4676-9df9-a7871acb1594)


2- Create a feature branch and make changes .
![Screenshot 2025-06-23 153420](https://github.com/user-attachments/assets/68b7cd72-540b-4d02-a2ff-373747bcb255)
             
              
              command : git checkout -b feature-branch
                       
created a new file feature.txt and append a line into it 

             command : echo "New Feature" >> feature.txt

to add this file 

              command : git add .

to commit the chnages 

             command : git commit -m "added new feature"

             
