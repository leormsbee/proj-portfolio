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
Debras-MacBook-Air:dev-2 debramoriarty$ ls -la
total 8
drwxrwxrwx   6 debramoriarty  staff   204 Mar  1 23:00 .
drwxrwxrwx   7 debramoriarty  staff   238 Feb 14 11:24 ..
-rwxrwxrwx   1 debramoriarty  staff   444 Mar  1 23:00 index.php
drwxrwxrwx  31 debramoriarty  staff  1054 Mar  1 22:50 proj-arcs
drwxrwxrwx  33 debramoriarty  staff  1122 Mar  1 22:54 proj-challies
drwxrwxrwx  31 debramoriarty  staff  1054 Mar  1 22:57 proj-debugacademy
Debras-MacBook-Air:dev-2 debramoriarty$ 


Save this file, then stage (git add) and commit your changes.  

Then:  
- `cd` to your proj-arcs repository  
- `cd` to sites/default
- Run `ls -la`
- Copy the information printed in the terminal  

Paste it here:  
Debras-MacBook-Air:dev-2 debramoriarty$ cd proj-arcs/
Debras-MacBook-Air:proj-arcs debramoriarty$ ls -la
total 520
drwxrwxrwx  31 debramoriarty  staff    1054 Mar  1 22:50 .
drwxrwxrwx   6 debramoriarty  staff     204 Mar  1 23:00 ..
drwxrwxrwx  13 debramoriarty  staff     442 Mar  1 22:50 .git
-rwxrwxrwx   1 debramoriarty  staff     174 Mar  1 22:50 .gitignore
-rwxrwxrwx   1 debramoriarty  staff    5969 Mar  1 22:50 .htaccess
-rwxrwxrwx   1 debramoriarty  staff  104070 Mar  1 22:50 CHANGELOG.txt
-rwxrwxrwx   1 debramoriarty  staff    1481 Mar  1 22:50 COPYRIGHT.txt
-rwxrwxrwx   1 debramoriarty  staff    1717 Mar  1 22:50 INSTALL.mysql.txt
-rwxrwxrwx   1 debramoriarty  staff    1874 Mar  1 22:50 INSTALL.pgsql.txt
-rwxrwxrwx   1 debramoriarty  staff    1298 Mar  1 22:50 INSTALL.sqlite.txt
-rwxrwxrwx   1 debramoriarty  staff   17995 Mar  1 22:50 INSTALL.txt
-rwxrwxrwx   1 debramoriarty  staff   18092 Mar  1 22:50 LICENSE.txt
-rwxrwxrwx   1 debramoriarty  staff    8681 Mar  1 22:50 MAINTAINERS.txt
-rwxrwxrwx   1 debramoriarty  staff    5382 Mar  1 22:50 README.txt
-rwxrwxrwx   1 debramoriarty  staff   10123 Mar  1 22:50 UPGRADE.txt
-rwxrwxrwx   1 debramoriarty  staff    6604 Mar  1 22:50 authorize.php
-rwxrwxrwx   1 debramoriarty  staff    1794 Mar  1 22:50 chmod.sh
-rwxrwxrwx   1 debramoriarty  staff     720 Mar  1 22:50 cron.php
drwxrwxrwx  49 debramoriarty  staff    1666 Mar  1 22:50 includes
-rwxrwxrwx   1 debramoriarty  staff     529 Mar  1 22:50 index.php
-rwxrwxrwx   1 debramoriarty  staff     703 Mar  1 22:50 install.php
drwxrwxrwx  72 debramoriarty  staff    2448 Mar  1 22:50 misc
drwxrwxrwx  43 debramoriarty  staff    1462 Mar  1 22:50 modules
drwxrwxrwx   6 debramoriarty  staff     204 Mar  1 22:50 profiles
-rwxrwxrwx   1 debramoriarty  staff    1479 Mar  1 22:50 robots.txt
drwxrwxrwx  13 debramoriarty  staff     442 Mar  1 22:50 scripts
drwxrwxrwx   6 debramoriarty  staff     204 Mar  1 22:50 sites
drwxrwxrwx   8 debramoriarty  staff     272 Mar  1 22:50 themes
-rwxrwxrwx   1 debramoriarty  staff   19986 Mar  1 22:50 update.php
-rwxrwxrwx   1 debramoriarty  staff    2200 Mar  1 22:50 web.config
-rwxrwxrwx   1 debramoriarty  staff     417 Mar  1 22:50 xmlrpc.php
Debras-MacBook-Air:proj-arcs debramoriarty$ 

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
