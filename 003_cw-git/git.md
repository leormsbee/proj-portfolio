# Intro to Git  
In this classwork assignment, we will learn git by using it.  

## Answering questions  
In this assignment, you will clone this repository, then edit this homework file itself (git.md) to answer the questions within the assignment. We will walk you through the steps for obtaining the file in the following steps. Your answers will be submitted as a pull request on github.   

### Clone the da-assignments repository  
- Log in to github.com  
- Visit:  ```https://github.com/debugacademy/da-assignments```  
- Press 'Fork' in the upper right corner of the page  
- You have just created a copy of this repository on your github account!  

### Git configuration  
- Open the command line (Windows: Git bash, Mac: Terminal)  
- Run: ```git --version``` to confirm git is working 
    - If you receive an error, git was not installed correctly  
- After replacing `[YOUR NAME]` with your name, run: `git config --global user.name "[YOUR NAME]"`  
- After replacing `[YOUR EMAIL]` with your e-mail, run: `git config --global user.email "[YOUR EMAIL]"`  
- Windows users only: Prevent windows from converting characters by running ```git config --global core.autocrlf false``` in your command line. 

### Git configuration for vagrant
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
- ```cd``` to the dev-1 folder (previously generated when we ran vagrant up):  
    - run ```cd ~/Desktop/debugacademy/sites/dev-1```    
- Clone the da-assignments repository that contains all homework and classwork assignments by running the following command in your command line:  
    - ```git clone https://github.com/debugacademy/da-assignments.git```  

This will create a copy of the da-assignments repository on your computer, in a folder named da-assignments, which will be placed where you ran the ```git clone``` command. In our case, the da-assignments folder will be placed inside debugacademy/sites/dev-1.  

Outside of the command line, confirm that the da-assignments folder now exists in the folder ~/Desktop/debugacademy/sites/dev-1.

Wonderful! You now have cloned this repository twice. Once in your github.com account, and once to your local computer. Let's proceed.  

### Create and switch to a new branch  
A branch is a version of your repository. We don't want to edit the 'master' branch - that version of your repository should continue to match that of Debug Academy's repository for the entire semester.  

- ```cd``` into the da-assignments folder
- Create a new branch based off of the master branch, which is our base branch in this case  
  - ```git checkout -b [new branch name] [base branch name]```  
- Name the branch using the following common convention  
  - [Topic]-[Task Number]-[Your initials]  

For example, Ashraf Abed would run the following command:  
  -```git checkout -b git-01-aa master```  

### Confirm you are on your new branch  
The ```git branch``` command lists all branches, and tells you what branch you are on by denoting it with ```*```  

Simply run the ```git branch``` command and confirm you are on the new branch you just created.  

### Make your first commit  
Git is great for keeping the history of all edits on files. Let's try it out by editing the file you're reading right now!  

Open this file from within your da-assignments folder using the Sublime Text 2 text editor program.  

- Fill in your name after this colon: 
  - [right here]  

You're not done quite yet. Changes saved to the git history must be deliberate; git does not save every edit you do to the history automatically. Imagine how long the list would be if it did!  

Stage your edit so that it will be included in the next commit:
- Save this file  
- In your command line window, cd into the da-assignments folder if you are not already there
- Run ```git status``` to see what files were modified.
- Run ```git add [filename]``` , after replacing [filename] with the name of this file    

Commit your edit!  
- In your command line window, run ```git commit -m '[my commit message]'```  , after replacing [my commit message] with a very short description of your changes.

### Compare branches  
You just switched from the master branch to your new branch, then made an edit and committed it to your new branch. Because branches are versions of the repository, we now have two different versions of the same repository! What does that mean?  

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
- Additionally, paste the URL to your remote in our classroom chat. We will use this soon.

Run ```git remote -v``` to see a list of all entries your repository has in its 'phone book'. Confirm that your github repository is listed, in addition to the Debug Academy remote, named 'origin'.  


### Push work to your github repository  
Let us now push the file we have been working on to our Github accounts. After all, a primary point of git is to be able to collaborate.  

`git push [your remote's nickname] [branch you would like to push]` 
- For example, Ali would run the following command: ```git push ali git-01-ah```  

Using the remote ('contact') entry from the previous task, git will send the specified branch to the remote which has the specified nickname in your contacts list.  

### Add your classmates as remotes
Let us now add two of our classmates as remote git connections so that we can send or receive work.
- Run the command: ```git remote add [nickname] [copied URL]```  
  - You need to know the url of your classmates' da-assignments repository.   
  - For example, if Ali wanted to add Ashraf as a remote, he would run the following command: ```git remote add ashraf https://github.com/ashabed/da-assignments.git```.  
  - Please retrieve a classmate's remote URL from our chatroom.  
- You should add a total of two classmates as git remotes.

Run `git remote -v` to confirm their remotes were added as contacts successfully.  

### Merging work  
We've edited this very file on our branch, and our classmates have edited it on their branches. What if we want to combine work from the two branches?  

- Switch to the branch you completed this assignment on  
  - `git checkout [my branch name]`  
      - If you are unsure of your branch's name, run `git branch`  
- Run ```git fetch --all``` to download work from all remotes  
- Run ```git branch -r``` to view a list of the remote branches available to us  
- Run ```git merge [Remote nickname]/[Remote branch name]``` to merge the work from your classmates remote into your local branch.  
- For example, if Ali wanted to Merge Ashraf's work, he would run the following command: ```git merge ashraf/git-01-aa``` 
- The edits you've made to your git.md file and the edits a classmate made to their git.md file should automatically be combined!

### Fix merge conflicts
Since you and your classmate edited the same exact file, there will be a conflict. Your terminal/gitbash will let you know of this, but you can see the actual conflict opening your git.md file in sublime text. Fix the merge conflict by separating you and your classmates names from question 1 through a comma. After this, commit your changes by repeating the following steps:
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

Review the pull request you are about to create, and confirm its creation. The folks at debugacademy will receive a notification, review your pull request, and merge in the work you have submitted!   
