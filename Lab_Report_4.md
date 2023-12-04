# Lab Report 4 - Vim
1. __Log into ieng6__

   ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/16f40b5e-68db-4b5b-9b62-93f34af667e9)

   Keys Pressed: ssh cs15lfa23tb@ieng6.ucsd.edu `<enter>`

   `ssh` to log into a remote machine. In our case, it's ieng6.

3. __Clone your fork of the repository from your Github account (using the SSH URL)__

   ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/6d280986-07b4-4c27-b2cf-cea14b7f04bf)

   Keys Pressed: git clone git@github.com:xIvanTKx/lab7.git `<enter>`

   `git clone` is used to create a copy of the repository in the home directory.

4. __Run the tests, demonstrating that they fail__

   ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/fd6703c3-3276-4a13-b917-5c380773fb5d)

   Keys Pressed: cd lab7 `<enter>`, ls `<enter>`, bash test.sh `<enter>`

   `cd` to change working directory to `lab7`, the one we just cloned. Then, `ls` to list all files/directories. Seeing there's a test script for the program, use `bash` to run the test shell script.

6. __Edit the code file to fix the failing test__

   ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/271339ee-6bef-4e65-b91c-8219038713c1)
   ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/a6a6a247-ea5d-4931-ab03-c61e954e02d1)

   Keys Pressed: vim ListExamples.java `<enter>`, `<up>` `<up>` `<up>` `<up>` `<up>` `<up>` `<shift + I>` `<right>` `<right>` `<right>` `<right>` `<right>` `<right>` `<backspace>` 2 `<esc>` `<shift + ;>` wq `<enter>`

   Since the cursor began at the bottom of the file after opening using `vim` text editor, I had to first navigate to the correct line using 6 `<up>` presses, then enter insert mode with `<shift + I>`, then navigate to the right character to delete and replace with `2` to make the fix. Lastly, `<esc>` to exit insert mode, then `<shift + ;>` to enter command console to type `wq` then `<enter>` to exit vim.
   
8. __Run the tests, demonstrating that they now succeed__

    ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/26946632-a715-48fb-bc03-99f4492461eb)

   Keys Pressed: bash test.sh `<enter>`

   Since we were still in the same working directory, I can just rerun the `test.sh` script to redo the tests.

10. __Commit and push the resulting change to your Github account (you can pick any commit message!)__

    ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/67824ee4-f07a-4e9d-aff6-3d996ca241ad)
    
    Keys Pressed: git add . `<enter>`, git commit -m "Update files" `<enter>`, git push origin main `<enter>`

    `git add` adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit.
    
    `git commit -m` captures a snapshot of the project’s currently staged changes. It’s like saving a version of your project. `-m` to include a brief description of the changes made.
    
    `git push` sends the committed changes to a remote repository. Usually `origin` for the original repository that you cloned and `main` for the main branch.
