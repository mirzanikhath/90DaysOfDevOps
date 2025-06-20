# Task 3: Configure Remote URL with PAT and Push/Pull

- Configuring remote URL using PAT(personal access token)

       command: git remote add origin https://<your-username>:<your-PAT>@github.com/<your-username>/90DaysOfDevOps.git

In the above command i have changed it as 

        command : git remote add origin https://mirzanikhath:<my PAT>@github.com/mirzanikhath/90DaysOfDevOps.git

But it shows Origin already exists.then i used the below command to set the URL 

         command : git remote set-url origin https://mirzanikhath:<myPAT>@github.com/mirzanikhath/90DaysOfDevOps.git




- Pushing my  Commit to Remote:

         command : git push -u origin main 




The above image shows my terminal where I'm trying to push the code to remote GitHub repository, but running into an issue and here's the breakdown how i solved it step by step 

when i run the command of git push 

           command : git push -u origin master 

I got an error like 

          error: failed to push some refs to .....
          hint : Updates were rejected because the tip of my current branch is behind its remote counterpart .

Which means Git is refusing to pysh because the localk master branch is behind the remote master branch.So i have done pulling the code first to sync the changes .




Now when I run git pull command the error occured as the changes need to be made in both local and remote git repository so I used rebase command here , which uses merge startegy to make changes both in local and remote repository .

                  command : git config pull.rebase false

After running this command it finally pulled and pushed the code to github.
