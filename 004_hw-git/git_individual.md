# Intro to Git
In this assignment, we will learn git by using it.

## Answering questions
In this assignment, simply edit the homework file itself to answer the questions on it. Your answers will be submitted as pull requests on github.

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be in your own words**

### To work on this assignment1. Open the homework assignment (the file you are reading) in a text editor, such as sublime text. You should have the 
da-assignments repository (folder) on your computer and inside your debugacademy directory, after cloning it during class.  

2. Use the command line (Terminal/Git bash) to create a new git branch, based off of the master branch, **for each question**. Follow the naming convention described below.

3. *After completing a question*, save the file in the text editor, then use the terminal (or git bash for windows) to add and commit the changes to the file.  

4. To start the next question, repeat steps 2-3.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review. *For this assignment, each question should be in its own commit.*  

## Questions
**For questions 1-8 below, create a new branch based off of the master branch using the following naming convention:**

*[Topic]-[Assignment Number]-[Question Number]-[Your initials]*

*For example, for question 1:*
Ashraf Abed would create a branch named: ```git-004-1-aa```

Upon completing a question, commit your changes to this file.

Protip: After editing this file, you can run ```git status``` to see what files were changed and ```git diff [file_name]``` to see what exactly was changed in the file.

### Question 1
- In your Terminal/Git Bash, use ```git checkout -b [Branch_Name]``` to create a new branch using the naming convention explained above.

Enter your name after this colon:

Then:
- Save this file.
- In your Terminal/Git Bash, ```git add``` this file so that it can be staged for inclusion in your next commit.
- In your Terminal/Git Bash, use the ```git commit -m "[Commit Message]"``` command to commit your changes and describe what the commit is for. **Note: You must replace [Commit Message] with a sentence of your own, briefly describing what you did to the file before git adding it**. An example commit message for this question can be, "Entered my name".

For example, these are the commands/steps I executed to complete question 1:
- ```git checkout -b git-004-1-aa```
- Made changes in the file by entering my name 
- Saved the file 
- Ran ```git status``` to see what files were changed
- Ran ```git diff [Name_Of_This_File]``` to see what changes were made
- ```git add hw_002_git/hw_002_git.md```
- ```git commit -m "Entered my name for question 1"```

You will generally repeat these steps for each question below, but you will adjust the branch names and commit messages accordingly.

### Question 2
- In your Terminal/Git Bash, create a new branch using the naming convention explained above. For example, I would run the following command ```git checkout -b git-004-2-aa```.

Briefly explain in your own words what it means to 'pull' in git:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 3
- In your Terminal/Git Bash, create a new branch using the naming convention explained above.

Briefly explain in your own words what it means to 'push' in git:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 4
- In your Terminal/Git Bash, create a new branch using the naming convention explained above.

Briefly explain in your own words what it means to 'rebase' in git:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 5
- In your Terminal/Git Bash, create a new branch using the naming convention explained above.

Briefly explain in your own words what it means to git 'checkout' a branch or commit:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 6
- In your Terminal/Git Bash, create a new branch using the naming convention explained above.

Use git log to list your most recent commit's ID. Type at least 5 characters from the commit ID here:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 7
- In your Terminal/Git Bash, create a new branch using the naming convention explained above.

Use git log to list the 2 most recent commits *before any of your own commits*. Type at least 5 characters from the two commit IDs here:
First commit ID:
Second commit ID:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 8
Create a new branch whose history matches the master branch exactly. Use the same naming convention for the branch as you have been for previous tasks.

Type the command you used to create this branch:

Then:
- Save this file.
- In your Terminal/Git Bash, use git to add this file.
- In your Terminal/Git Bash, use git to commit this file along with a commit message.

### Question 9
Create a new branch whose history matches the master branch exactly. Use the same naming convention for the branch as you have been for previous tasks.
1. Create a branch named ```git-002-bonus``` based off of the `master` branch
2. Merge all of the branches you created for this homework assignment into this branch
  - Use the git merge ```[branch_to_merge]``` command to merge another branch into the branch you are currently on
  - Witness the usefulness of git

## Submitting your assignment

### Step 1
Push all of the branches you created for your homework assignment to your forked copy of the da-assignments repo, one by one.

- In your Terminal/Git Bash, use the ```git push [Name_Of_Remote_Repository] [Branch_Name]``` to push each branch up to the da-assignments github repository. To find out the name of the remote repository, use the ```git remote -v``` command. To get a list of the branches you have created, use the ```git branch``` command.
- For example, to push up my branch from question 1, I would run the following command: ```git push ashraf git-004-1-aa```. To push up my work from question 2, I would run the following command: ```git push ashraf git-004-2-aa``` and so on.

### Step 2
Create pull requests to the class' assignments repo for each branch that you pushed. There will be one pull request per branch.
- Using a browser, navigate to https://github.com/debugacademy/da-assignments and create a pull request. You should see a notification alerting you of the branch you have just pushed up using git alongside a "Create Pull Request" button.

## Assigned Reading
Read the lessons on git commands and git flow. You are not expected to memorize this information, google will always be available. But any top employer will expect you to have a solid understanding of the information in the lessons.
