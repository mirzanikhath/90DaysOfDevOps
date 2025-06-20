# Task 5: Advanced Branching and Switching

- Created a new branch feature-update and switched to that branch by using 

        command : git checkout -b feature-update

![Screenshot 2025-06-20 145159](https://github.com/user-attachments/assets/f633d7b1-efcd-4319-a6d2-d59185fa6b4a)


- Modified the File info.txt and Committed Changes to the new branch and further pushed to remote github repository  :

           command :git add info.txt
                    git commit -m "Feature update: Enhance info.txt with additional details"
                    git push origin feature-update
![Screenshot 2025-06-20 172331](https://github.com/user-attachments/assets/ad2c5df4-1a9f-4c84-8b17-c8b471dc2b05)

![Screenshot 2025-06-20 172406](https://github.com/user-attachments/assets/b17c17e0-d317-4b10-991a-6add1b5b60da)


- merging the feature-update branch with master branch through creating a pull request on github 

# Step-1: 
Go to pull requests click on New pull request option which is in green color 

![Screenshot 2025-06-20 173347](https://github.com/user-attachments/assets/c1b95f80-0499-4cdb-adc9-14df959edcdc)

# Step-2:
Enter the base branch in which we have to merge our compare branch as you can see below .

base branch:master                              compare branch:feature-update

then click on create pull request option.

![Screenshot 2025-06-20 173442](https://github.com/user-attachments/assets/de354f4d-21e0-4b17-9184-1c18c334952d)

# Step -3:
The page will be displayed as shown in the figure below which gives us breif about what are being merged from feature-update branch into master branch and verify the conflicts present if no conflicts are present then click on merge pull request option.

![Screenshot 2025-06-20 173626](https://github.com/user-attachments/assets/1766c084-5a0b-4796-b42c-72bd0372d385)

# Step-4:
Finally the feature-update branch is being merged in master branch . Now we can easily delete the feature-update branch if we want .

![Screenshot 2025-06-20 173727](https://github.com/user-attachments/assets/f848b173-396e-47d0-be52-3343aad31d81)







