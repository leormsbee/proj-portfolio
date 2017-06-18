# Intro to Git  
In this classwork assignment, we will learn git by using it.  

## Answering questions  
In this assignment, you will fork (and clone, if you haven't already) this repository, then edit this homework file itself (git.md) to answer the questions within the assignment. We will walk you through the steps for obtaining the file in the following steps. Your answers will be submitted as a pull request on github.   

### Fork the da-assignments repository  
- Log in to github.com  
- Visit:  ```https://github.com/debugacademy/da-assignments```  
- Press 'Fork' in the upper right corner of the page  
- You have just created a copy of this repository on your github account!  

### Git configuration  
- Open the command line (Windows: Git bash, Mac: Terminal)  
- Run: ```git --version``` to confirm git is working 
    - If you receive an error, git was not installed correctly  
- After replacing `[YOUR NAME]` with your name, run: `git config --global user.name "[YOUR NAME]"`  
- After replacing `[YOUR EMAIL]` with your public e-mail, run: `git config --global user.email "[YOUR EMAIL]"`  
- Windows users only: Prevent windows from converting characters by running ```git config --global core.autocrlf false``` in your command line. 

### Git configuration for vagrant
**If your vagrant environment is not yet set up, skip this section.**  

- cd into your academyvm folder  
  - `cd ~/Desktop/debugacademy/academyvm`  
- Enable your vagrant environment by running vagrant up  
  - `vagrant up`  
- Enter your virtual machine's bash window, or shell, using the ssh (secure shell connection) command
  - `vagrant ssh`
- After replacing `[YOUR NAME]` with your name, run: `git config --global user.name "[YOUR NAME]"`  
- After replacing `[YOUR EMAIL]` with your e-mail, run: `git config --global user.email "[YOUR EMAIL]"`  
- Exit your vagrant environment
  - `exit`

### Assignments repository set up
**If you have already cloned the da-assignments folder into debugacademy, skip this step.**
- ```cd``` to the debugacademy folder
- Clone the da-assignments repository that contains our assignments by running the following command in your command line:  
    - ```git clone https://github.com/debugacademy/da-assignments.git```  

This will create a copy of the da-assignments repository on your computer, which will be placed where you ran the ```git clone``` command.  

Outside of the command line, confirm that the folder now exists in the folder ~/Desktop/debugacademy/da-assignments.

You have now cloned this repository twice. Once in your github.com account, and once to your local computer. Let's proceed.  

### Create and switch to a new branch  
A branch is a version of your repository. Just like on a real gitflow-based project, we never want to edit the 'master' or 'master' branches directly. Those versions of your repository should continue to match that of Debug Academy's repository for the entire project.  

- ```cd``` into the da-assignments folder
- Create a new branch based off of the *master* branch, which is our base branch using the gitflow workflow  
  - ```git checkout -b [new branch name] [base branch name]```  
- Name the branch using the following common convention  
  - [Topic]-[Task Number]-[Your initials]  

For example, Ashraf Abed would run the following command:  
  -```git checkout -b git-003-aa origin/master```  

### Confirm you are on your new branch  
The ```git branch``` command lists all branches, and tells you what branch you are on by denoting it with ```*```  

Simply run the ```git branch``` command and confirm you are on the new branch you just created.  

### Make your first commit  
Git is great for keeping the history of all edits on files. Let's try it out by editing the file you're reading right now!  

Open this file from within your da-assignments folder using the Sublime Text 3 text editor program.  

- Fill in your names after this colon:
  - Ashraf
  - Wendy
  - Brandt
  - Divyesh
  - Luanne
  - Leila
  - Sajid

You're not done quite yet. Changes saved to the git history must be deliberate; git does not save every edit you do to the history automatically. Imagine how long the list would be if it did!  

Stage your edit so that it will be included in the next commit:
- Save this file  
- In your command line window, cd into the da-assignments folder if you are not already there
- Run ```git status``` to see what files were modified.
- Run ```git add [filename]``` , after replacing [filename] with the name of this file    

Commit your edit!  
- In your command line window, run ```git commit -m '[my commit message]'```  , after replacing [my commit message] with a very short description of your changes.

### Compare branches  
You just switched from the master branch to your new branch, then made an edit and committed it to your new branch. Because branches are versions of the repository, we now have multiple different versions of the same repository. What does that mean?  

It means that you can simply switch between ("checkout") your master branch and your new branch, and all of the files in your da-assignments folder will automatically be updated to the appropriate version!  

Let's try it out. You committed your name above, let's see if it really is only on your new branch.  
- Look at your file in sublime text. Confirm the change you made (entering your name) is there
- In the command line, switch back to the master branch. ```git checkout master```  
- Reload the file and look for the change you made, if you are on your master branch you should not see it  

### Communicating with remotes  
You've made updates to your local branch, now you want to share those updates with teammates. This is where 'remotes' come in.    

Adding a remote is like adding a contact to your phone book. Instead of adding a name and phone number, you add a name and git URL. The concept and governing rules are the same.  

Go to your github account, and in the "Your repositories" section, click on the da-assignments repository which you forked.  
- Under the "Clone or Download" button, copy the ```HTTPS clone URL```    
- Run the command: ```git remote add [nickname] [copied URL]``` .
  - Just like a contact in your phone, you can enter any name you want for the `[nickname]`
- For example, Ali would run the following command: ```git remote add ali https://github.com/AliHassan7/da-assignments.git```
  - This command will add a contact in your 'phonebook', or list of remotes, with your github account's repository.  
- Additionally, paste share the URL of your remote with your instructor. We will use this soon.

Run ```git remote -v``` to see a list of all entries your repository has in its 'phone book'. Confirm that your github repository is listed, in addition to the Debug Academy remote, named 'origin'.  


### Push work to your github repository  
Now push the file we have been working on to our Github accounts. After all, a primary point of git is to be able to collaborate.  

`git push [your remote's nickname] [branch you would like to push]` 
- For example, Ali would run the following command: ```git push ali git-003-ah```  

Using the remote ('contact') entry from the previous task, git will send the specified branch to the remote which has the specified nickname in your contacts list.  

### Add your classmates as remotes
Now add two of our classmates as remote git connections so that we can send or receive work.
- Run the command: ```git remote add [nickname] [copied URL]```  
  - You need to know the url of your classmates' da-assignments repository.   
  - For example, if Ali wanted to add Ashraf as a remote, he would run the following command: ```git remote add ashraf https://github.com/ashabed/da-assignments.git```.  
  - Please retrieve all classmate's remote URLs.  

Run `git remote -v` to confirm their remotes were added as contacts successfully.  

### Merging work  
We've edited this very file on our branch, and our classmates have edited it on their branches. What if we want to combine work from the two branches?  

- Switch to the branch you completed this assignment on  
  - `git checkout [my branch name]`  
      - If you are unsure of your branch's name, run `git branch`  
- Run ```git fetch --all``` to download work from all remotes  
- Run ```git branch -r``` to view a list of the remote branches available to us  
- Run ```git merge [Remote nickname]/[Remote branch name]``` to merge the work from your classmates remote into your local branch.  
- For example, if Ali wanted to Merge Ashraf's work, he would run the following command: ```git merge ashraf/git-003-aa``` 
- The edits you've made to your git.md file and the edits a classmate made to their git.md file should automatically be combined!

### Fix merge conflicts
Since you and your classmate edited the same line in the same file, there will be a conflict. Your terminal/gitbash will let you know of this, but you can see the actual conflict opening your git.md file in sublime text. Fix the merge conflict by separating you and your classmates names from question 1 through a comma. After this, commit your changes by repeating the following steps:
- Save this file  
- In your terminal, run ```git status``` to see what files were modified.
- In your terminal, run ```git add [filename]```    
Commit your edit!  
- In your terminal, run ```git commit -m '[my commit message]'``` 
- A sample commit message could be 'Merged Ashraf's git file'
- Repeat the steps in the "Merging work" section, but for a different classmate this time
- Push your work to your fork of the da-assignments repository on github by repeating the steps under the heading "Push work to your github repository"  

### Create a pull request  
Now that you've merged your edits to the git.md file (the file you are reading) along with the edits of two other classmates, it's time to submit your work from your github repository to the main debugacademy repository.  

Because you don't have permission to your work to debugacademy's account, you must instead ask debugacademy to pull the work from your account. This is called creating a 'Pull Request', and it is a feature on github.com .  

Once you've pushed your branch to your github repository, visit your github repository, and click 'Create Pull Request' or 'Pull Requests'.  
By default, the pull request will be created 'against', or to, the master branch. However, because we are following the gitflow workflow we want the pull request to be 'against' the master branch. Click 'Create pull request', but review its settings closely and ensure the pull request is created against the master branch, not the master branch.  

The folks at debugacademy will receive a notification, review your pull request, and merge in the work you have submitted!   

### Create another new branch  
While waiting for the "release master" to review and merge our work, we want to work on another task.  

Create a new branch based off of master like so: `git checkout -b git-003-aa-2 master`  

Simply write today's date here: [Right here].

Commit your changes to this file to your new branch and push your work to your github fork.  
## Master and master have been updated
Follow along with the instructor to see your work merged in. The work being merged into the "production" repository has team-wide implications.  

### Update your master branch  
Now that the "prod" master branch has been updated, you must update:  
- Your local master branch
- Your fork's master branch

First, checkout your master branch:  
- `git checkout master`  

Then, compare your master branch to origin's:  
- `git branch -u origin/master`  
  - One-time command. Specifies which remote branch to compare your local branch with.  
- `git fetch --all`  
  - Fetches all remote branches.  
- `git status`  
  - Will now display whether your local master branch is ahead, behind, or even with origin's master branch.  

If your master branch is behind origin's master branch, as it should be, run:  
- `git pull origin master`  

Then confirm it is now up-to-date:  
- `git status`  

### Update your feature branch
This update has wider implications - now our new feature branch is "behind" master and master, because we created it before we the branches were updated. Thankfully, git has the rebasing feature to address this situation.  

This can be resolved in a few easy steps:
- Go to your feature branch  
- Run: `git rebase master`  

This will put the commits from the master branch *before* the new commits on your feature branch.

### Conflicting updates
What if the updates had conflicted? Your teacher is updating the master branch with an update which conflicts with your newest feature branch. Work with the group to place the latest updates from the master branch before the updates from your feature branch.  
