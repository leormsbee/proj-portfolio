# Building ARCS, debugacademy.com, challies.com
In this assignment, we will begin building our first clients' Drupal websites, while gaining more practice with git.  

## Answering questions
For this assignment, you will be committing changes to:  
- 006_install_local_sites.md (the file you are reading)
- Your (new) proj-debugacademy repo
- Your (new) proj-arcs repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```dev-setup-006-aa```  

### Download new site repos

1- Clone the ARCS project repository from github  
- Github repo: https://github.com/debugacademy/proj-arcs
- Clone it into your sites/dev-2 folder
  - cd to your sites/dev-2 folder
  - Then run: git clone https://github.com/debugacademy/proj-arcs.git

2- Clone the challies project repository from github, if you have not done so previously  
- Github repo: https://github.com/debugacademy/proj-challies
- Clone it into your sites/dev-2 folder
  - cd to your sites/dev-2 folder
  - Then run: git clone https://github.com/debugacademy/proj-challies.git

3- Clone the debugacademy project repository from github  
- Github repo: https://github.com/debugacademy/proj-debugacademy
- Clone it into your sites/dev-2 folder
  - cd to your sites/dev-2 folder
  - Then run: git clone https://github.com/debugacademy/proj-debugacademy.git

4- Clone the public_html project repository from github  
- Github repo: https://github.com/debugacademy/public_html
- Clone it into your sites/php folder
  - cd to your sites/php folder
  - Then run: git clone https://github.com/debugacademy/proj-debugacademy.git

### Create index.php
- Open the folder debugacademy/sites/dev-2
- Create a new file named ```index.php``` using sublimetext or notepad++
- Place the following code in the file, then save the file:
```
<h1>Websites on dev-2</h2>
<?php
// set to current directory 
$dir = '';
// directories only. ignore files, etc.
foreach(glob($dir.'*', GLOB_ONLYDIR) as $folder){ 
  // do not include wordpress directories
  if (($folder != 'wp-admin') && ($folder != 'wp-content') && ($folder != 'wp-includes')) { 
    // list directories and their links
    ?> 
    <li><a href="<?php echo $dir."/".$folder;?>"><?php echo $folder;?></li> 
    <?php 
  }
} 
?>
```

### Install ARCS website using Drush
- Step 1: cd to your Vagrant box (academyvm), and ensure it is running:
  - `vagrant up`
- Step 2: copy proj-arcs/sites/default/default.settings.php to proj-arcs/sites/default/settings.php
- Step 3: copy proj-arcs/sites/default/default.settings.local.php to proj-arcs/sites/default/settings.local.php
- Step 4: edit the new settings.local.php file
  - Replace ```[DATABASE NAME HERE]``` with a name for your database
    - Database names should only contain lowercase letters, numbers, and underscores
    - For example: ```dev2_arcs``` is a good database name
- Step 5: cd to your Vagrant box (academyvm), and connect to your virtual machine's command line using the `vagrant ssh` command:
  - `vagrant ssh`
- Step 6: cd to: ```/var/www/dev-2/proj-arcs```
- Step 7: Run: ```drush site-install -y```
- Step 8: Run ```exit``` to leave your vagrant box's command line and return to your own
- Step 8: In your browser, visit: dev-2.academyvm.dev , then click 'proj-arcs'
- Step 9: Your Drupal website should be set up!




- Step 3: Visit dev-2.academyvm.dev , then click 'proj-arcs'
  - Choose the 'standard' profile
  - Follow the installation instructions. 
    - Your database name is: dev2_arcs
    - Your database username is: root
    - Your database password is: root




- Step 1: from the same folder, connect via SSH: 
  - `vagrant ssh`
- Step 2: Create MySQL database named `dev2_arcs` in vagrant environment:
  - `mysql -uroot -proot -e 'create database dev2_arcs;'`
    - You have created a database named 'dev2_arcs', by using your MySQL username and password of 'root'.
- Step 3: Visit dev-2.academyvm.dev , then click 'proj-arcs'
  - Choose the 'standard' profile
  - Follow the installation instructions. 
    - Your database name is: dev2_arcs
    - Your database username is: root
    - Your database password is: root


- Step 5: Edit the section of code you just pasted to include the following:
  - Set the 'username' as 'root'
  - Set the 'password' as 'root'
  - Set the 'database' as the database name you used in Step 2
- Step 6: Follow the instructions shown at ha.academyvm.dev
  - Select the 'standard' profile
- Commit your updated settings.php file
- Submit a pull request to the site's repo with your updated settings.php file

### Install DebugAcademy website using the GUI
- Step 1: cd to your Vagrant box, and ensure it is still running: 
  - `vagrant up`
- Step 2: SSH into your vagrant machine:
  - `vagrant ssh`
- Step 3: Create MySQL database named `dev2_debugacademy` in vagrant environment:
  - `mysql -uroot -proot -e 'create database dev2_debugacademy;'`
    - You have created a database named 'dev2_debugacademy', by using your MySQL username and password of 'root'.
- Step 4: Exit vagrant's command line: `exit`
- Step 5: Open the folder sites/dev-2/proj-debugacademy
- Step 6: Within that folder, copy the file sites/default/default.settings.php to sites/default/settings.php
- Step 7: Visit: dev-2.academyvm.dev/proj-debugacademy/install.php
  - Follow the installation instructions, with the following settings:
  - Choose the *Standard* profile
  - When prompted for the database information:
    - Database name: dev2_debugacademy
    - Database username: root
    - Database password: root
- Step 8: Continue then complete the installation

### Submit your assignment
You'll be submitting the following:  

#### This file
After completing all of the above steps, do this:
- `cd` to your sites/dev-2 repository  
- Run `ls -la`
- Copy the information printed in the terminal 

Paste it here:  

Save this file, then stage (git add) and commit your changes.  

Then:  
- `cd` to your proj-arcs repository  
- `cd` to sites/default
- Run `ls -la`
- Copy the information printed in the terminal  

Paste it here:  

Save this file, then stage (git add) and commit your changes.  

Then:  
- `cd` to your proj-debugacademy repository  
- `cd` to sites/default
- Run `ls -la`
- Copy the information printed in the terminal

Paste it here:  

Save this file, then stage (git add) and commit your changes.  

**Pull request #1:** Submit a pull request from your da-assignments repository with the branch containing what you pasted in this file.  

#### Debug Academy repository
##### Add a module to the website
- Open the folder: sites/dev-2/proj-debugacademy/sites/all/modules.
- Create a subfolder named 'contrib'.
- Right click and save the most stable ('green') version of the views module from the bottom of this page: drupal.org/project/views
- Unzip the file you saved to retrieve the folder named 'views'
- Place the folder named 'views' inside the 'contrib' folder you just created
- Log in to dev-2.academyvm.dev/proj-debugacademy
- Visit the 'modules' administration page
- Confirm that you see the 'views' module in the list of available modules.

##### Submit your module addition as a pull request
- Log in to github.com, if you are not already logged in
- Visit https://github.com/debugacademy/proj-debugacademy
- Click 'Fork' in the top right portion of the page
- Copy the 'git clone' URL to your fork
- cd to your proj-debugacademy repository
- Use the 'git remote add' command (see lesson 005) to add an remote alias to your fork
  - This will allow you to push to and pull from your fork
- Create a new git branch named da-views-[your initials], based off of master
  - 'da' stands for the site we are currently working on
- Stage (git add) and commit the entire folder named 'views' to your new branch
- Push the branch to your fork using the remote alias you just added
- Create a pull request to the debugacademy/proj-debugacademy repository with your branch

#### ARCS repository
##### Add a module to the website
- Open the folder: sites/dev-2/proj-arcs/sites/all/modules.
- Create a subfolder named 'contrib'.
- Right click and save the most stable ('green') version of the views module from the bottom of this page: drupal.org/project/views
- Unzip the file you saved to retrieve the folder named 'views'
- Place the folder named 'views' inside the 'contrib' folder you just created
- Log in to dev-2.academyvm.dev/proj-arcs
- Visit the 'modules' administration page
- Confirm that you see the 'views' module in the list of available modules.

##### Submit your module addition as a pull request
- Log in to github.com, if you are not already logged in
- Visit https://github.com/debugacademy/proj-arcs
- Click 'Fork' in the top right portion of the page
- Copy the 'git clone' URL to your fork
- cd to your proj-arcs repository
- Use the 'git remote add' command (see lesson 005) to add an remote alias to your fork
  - This will allow you to push to and pull from your fork
- Create a new git branch named ar-views-[your initials], based off of master
  - 'ar' stands for the site we are currently working on
- Stage (git add) and commit the entire folder named 'views' to your new branch
- Push the branch to your fork using the remote alias you just added
- Create a pull request to the debugacademy/proj-arcs repository with your branch