# Task 4: Cherry-Picking - Selectively Apply Commits

- Cherry picking means picking a specific commit form one branch and applying it onto another branch. Instead of merging the entire branches , you choose only the commits you want. 
- When we make an important fix  on one branch and want that same fix on another branch. Which means we eant only some commits not the entire history. 
- Cherry pick creates a new commit with a new hash.It can cause conflicts , if the changes don't fit cleanly.Useful for selective merging . 

Scenario: A bug fix exists in another branch, and you only want to apply that specific commit.

- Find the commit to cherry-pick.
 
                  command: git log --oneline
![Screenshot 2025-06-30 154029](https://github.com/user-attachments/assets/d6b054bb-862a-4abd-89f1-bd82443fa091)

- Apply a specific commit to the current branch.

                 command : git cherry-pick df84934

  ![Screenshot 2025-06-30 154153](https://github.com/user-attachments/assets/761f8ded-5f2f-45c0-a9f8-837511cb6e4b)


- To resolve the conflicts and again running git cherry-pick 

                 command: git cherry-pick --continue

# How cherry-picking is used in bug fixes :

Imagine the situation:

- we fix a bug on one branch (e.g develop)
- we also need to fix on another branch , but we don't want to merge the entire branch . So , instead of merging everything , i am using cherry-pick just the bug fix commit. 

# Risk of cherry picking:

There are many risks while using cherry-pick command :
- It creates a duplicate commits which means possible duplicate code changes or merge conflicts down the line .
- Conflicts : Cherry-pick changes cannot smoothly fit in the new branch we might have bugs and if they are not resolved carefully then the conflicts rate will increase . 
- Context Loss: Cherry-picking just one commit may break functionality because supporting changes are missing. 
- Complex history : Frequent cherry-picking makes the commit history more complex to read and track the changes . 
- Accidental overwrites: If we cherry-pick a commit that makes changes already modified differently in the target branch, we could overwrite desired changes . 

To minimize the risks of chery picking :
- Avoid the cherry-picking fo partial changes that depends-on other unmerged commits.
- keep good commit messages to clarify the commits . 
- Before pushing , review the changes carefully .
- Avoid cherry-picking for large and complex commits. 
- communicate with our team so that they get clear image what is cherry-picked and committed . 
