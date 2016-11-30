# Installing AcademyThemes and ARCS
In this assignment, we will begin building our portfolio Drupal website alongside a non-profit Drupal website while gaining more practice with git.  

## Answering questions
For this assignment, you will be committing changes to:  
- cw_002_site_install.md (the file you are reading)
- Your (new) proj-themes repo
- Your (new) proj-arcs repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-install-sites-002-aa```  

### Download new site repos

1- Clone the theme portfolio project repository from github  
- Github repo: https://github.com/debugacademy/proj-themes
- Clone it into your sites/dev-1 folder
  - cd to your sites/dev-1 folder
  - Then run: git clone https://github.com/debugacademy/proj-themes.git

2- Clone the ARCS project repository from github  
- Github repo: https://github.com/debugacademy/proj-arcs
- Clone it into your sites/dev-1 folder
  - cd to your sites/dev-1 folder
  - Then run: git clone https://github.com/debugacademy/proj-arcs.git

### Create index.php for every environment
- Open the folder debugacademy/sites/dev-1
- Create a new file named ```index.php``` using sublimetext.
- Place the following code in the file, then save the file:
```
<h1>Websites on this environment</h2>
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

Afterwards, copy the file you just created (index.php) to each of your other environments - dev-2, stage-1, stage-2, 

### Install the theme portfolio website using the GUI
- Step 1: cd to your Vagrant box, and ensure it is still running: 
  - `vagrant up`
- Step 2: SSH into your vagrant machine:
  - `vagrant ssh`
- Step 3: Create MySQL database named `dev1_themes` in vagrant environment:
  - `mysql -uroot -proot -e 'create database dev1_themes;'`
    - You have created a database named 'dev1_themes', by using your MySQL username and password of 'root'.
- Step 4: Exit vagrant's command line: `exit`
- Step 5: Open the folder sites/dev-1/proj-themes
- Step 6: Within that folder, copy the file sites/default/default.settings.php to sites/default/settings.php
- Step 7: Visit: dev-1.academyvm.dev/proj-themes/install.php
  - Follow the installation instructions, with the following settings:
  - Choose the *Standard* profile
  - When prompted for the database information:
    - Database name: dev1_themes
    - Database username: root
    - Database password: root
- Step 8: Continue then complete the installation

### Install ARCS website using Drush
- Step 1: cd to your Vagrant box (academyvm), and ensure it is running:
  - `vagrant up`
- Step 2: cd to your Vagrant box (academyvm), and connect to your virtual machine's command line using the `vagrant ssh` command:
  - `vagrant ssh`
- Step 3: copy proj-arcs/sites/default/default.settings.php to proj-arcs/sites/default/settings.php
  - `cd /var/www/dev-1/proj-arcs/sites/default`
  - `cp default.settings.local.php settings.local.php`
- Step 4: copy proj-arcs/sites/default/default.settings.local.php to proj-arcs/sites/default/settings.local.php
  - `cp default.settings.php settings.php`
- Step 5: edit the new settings.local.php file using sublimetext
  - Enter a name for your database
    - Database names should only contain lowercase letters, numbers, and underscores
    - For example: ```dev1_arcs``` is a good database name
  - Fill in the site's URL for the `$base_url` variable. 
    - `$base_url = 'http://dev-1.academyvm.dev/proj-arcs';`
- Step 6: Run: ```drush site-install -y```
- Step 7: In your browser, visit: dev-1.academyvm.dev , then click 'proj-arcs'
- Step 8: Your Drupal website should be set up!

### Submit your assignment
You'll be submitting the following:  

#### This file
After completing all of the above steps, do this:
- `cd` to your sites/dev-1 repository  
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
- `cd` to your proj-themes repository  
- `cd` to sites/default
- Run `ls -la`
- Copy the information printed in the terminal

Paste it here:  

Save this file, then stage (git add) and commit your changes.  

**Pull request #1:** Submit a pull request from your da-assignments repository with the branch containing what you pasted in this file.
