# Classwork - Advanced Git.
In this classwork assignment, we will learn to use advanced git commands.

## Answering questions
For this assignment, you will be committing changes to:  
- Your da-assignments repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review. Before starting any assignment, you should checkout the master branch and then update it by running ```git pull [remote] master```. The remote's name should be the remote that points to https://github.com/debugacademy/da-assignments.git.

**cd into your da-assignments repo and create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Question Number]-[Your initials]**  

For example: Ashraf Abed would create a branch with the following name: ```cw-git-023-aa```.

## Tasks
1 - Use ```git show [commit id]``` to show a specific commit's changes.
- Use `git log` to see a list of commits. You can scroll using your keyboard's up and down keys.
- Find the commit id of the commit which says "Added note for Windows users.".
- Copy the first five characters of the commit ID., then press `q` to leave the git log.
- Run ```git show [commit id]``` , replacing `[commit id]` with the five character commit id you just copied.
- The file(s) that were modified and/or added in this commit should be displayed. Paste the name(s) of those files below this line:

- Press `q` to exit the `git show` command.
- Git add this file
- Git commit this file and for a commit message, type "Answered question 1". 

2 - Use ```git add -p``` to specify which portions of files to commit.
  - Create a new branch based off of the master branch for this task, using the following branch naming convention: ```cw-git-023-02-initials```
  - cd into da-assignments/files/continuousgood/
  - Open the style.css file in your favorite text editor, such as sublime text.
  - Add temporary code to the top of the file. After that, add temporary code to the very bottom of the file. Save the styles.css file.
  - Run ```git status``` to see which files were edited
  - Run ```git add -p```. Choose to stage (`y`) the first hunk, or portion of code edited, and deny staging the second one (`n`).
  - Run ```git status```
  - You will see that the styles.css file was staged. Commit the change.
  - Use ```git show``` to see which changes were committed.

3 - Use the ```git merge [branchname]``` command to place commits from different branches *after* your own.
  - Create a new branch based off of the master branch for this task, using the following branch naming convention: ```cw-git-023-03-initials```
  - On this new branch, cd to da-assignments/files/continuousgood/ and copy the homepage.html file and place it into the images folder. Verify that the file has been copied.
  - Git add and commit this file
  - Switch back to (checkout) your branch from question 2. If you look into da-assignments/files/continuousgood/images, you will notice that the file we just placed into to the images folderis no longer there. That is because our commit was on our question 3 branch, not on our question 2 branch. 
  - We want to take the commits from your question 3 branch and put them on our question 2 branch. This is where a merge can come in handy.
  - Merge the question 3 branch into your question 2 branch using the `git merge [branchname]` command. Replace `[branchname]` with the name of the branch you are merging into your currently checked out branch.
  - Check to see if the homepage.html file is in the images folder. Below, paste the latest commit message:


4 - Use the ```git rebase [branchname]``` command to place commits from different branches *before* your own
  - Imagine the master branch was updated before you pushed your work. This command allows you to place the master branch's commits before your own, without you having to redo your work.
  - Create a new branch based off of the master branch for this question, using the following branch naming convention: ```cw-git-023-04-initials```
  - Make a change **to the top of** the styles.css file, then git add and commit it. Paste your commit message below this line. You can use `git show` to see your commit:

  - Checkout your question 3 branch. Edit and make a change **to the bottom of** the styles.css file. Git add and commit it. Paste your commit message below this line: 

  - The question 3 branch has commits that the question 4 branch doesn't have. Git rebase will allow us to place the commits from the question 3 branch *before* our commits on the question 4 branch.

  - Check out our question 4 branch.
  - Run ```git rebase [question 3 branch]```
    - If you are taken to a screen for typing a message, you can simply press `:wq` to save and exit the vim text editor.
  - Run ```git log``` to see the order of the commits. Your question 3 commits should appear before your question 4 commits! Paste the last two commits below this line:

5 - Use ```git cherry-pick [commit id]``` to bring 1 specific commit to your branch
  - Let us say we want to take one specific commit from a branch and put it on another branch. This is where the ```git cherry-pick [commit id]``` command comes in handy.
  - Checkout your branch from question 1 , run git log, and copy the first 5 characters from the commit id of the commit that says "Answered question 1". 
  - Create a new branch based off **of the master branch** for this question, using the following branch naming convention: ```cw-git-023-05-initials```
  - On the question 5 branch, run ```git cherry-pick [commit id]``` , replacing `[commit id]` with the commit you copied earlier in this question.
  - Run `git log` to confirm you have brought that specific commit to this branch! Paste the last two commits below this line:


6 - Use ```git branch -u [remote/branch]``` to 'track' a remote branch
  - Checkout your question 5 branch
  - To easily compare your question 5 branch to the remote master branch, run ```git branch -u origin/master```
    - Replace 'origin' with your alias for the debug academy repository.
  - Now, to see if your branch is ahead/behind, simply run: `git fetch --all`, then `git status` .
  - A message will be printed which says whether your branch is ahead of or behind the branch you are tracking.
  - This command is very useful to see if you need to update your branch.
  - Paste the output of `git status` here:

7 - Use ```git branch -u [remote/branch]``` to 'track' a remote branch
  - Checkout your question 4 branch
  - To easily compare your question 4 branch to the remote master branch, run ```git branch -u origin/master```
    - Replace 'origin' with your alias for the debug academy repository.
  - Now, to see if your branch is ahead/behind, simply run: `git fetch --all`, then `git status` .
  - A message will be printed which says whether your branch is ahead of or behind the branch you are tracking.
  - This command is very useful to see if you need to update your branch.
  - Paste the output of `git status` here:
  
8 - Use ```git reset [commit id]``` to undo commits without losing your work
  - If we committed work prematurely, or included too much in the commit, we can undo the commit without losing our work.
  - Simply specify the last commit id *that you want to keep*
  - Create a new branch based off of the master branch for this question, using the following branch naming convention: ```cw-git-023-08-initials```
  - Edit styles.css, add and commit your work.
  - Use `git log` to confirm your commit is there. 
  - Copy the commit ID of the commit *before* your most recent commit
  - Run `git reset [commit id]`, pasting the commit ID you copied in place of [commit id] 
  - Run `git log` to confirm the last commit you made is no longer there
  - Run `git status` to confirm your work is still there

9 - Use ```git reset [remote/branch or commit id] --hard``` to delete your work and match a branch or commit id
  - Stay on your branch from question 8. Run git status to confirm you have uncommitted work.
  - Let us say that we want to throw away our work in progress, and make our branch match the master branch exactly. 
  - Run ```git reset [remote/master] --hard```
  - This will throw away (permanently) all work on our current branch, and make our current branch match the remote/master branch exactly.
  - Run git log to confirm that your branch now matches the master branch exactly.
  - Paste the output of your log below this line:

  - This command is especially useful to remove any work we committed directly to or master branches. It ensures that our branch is fully corrected.

## Submitting your assignment
### Step 1
Push branches 1, 3, 4, and 5 of this assignment to your fork of the da-assignments repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the each of the branches you pushed.
