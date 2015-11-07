# Building HA Lighting
In this assignment, we will begin building our first clients Drupal websites.  

## Answering questions
For this assignment, you will be committing changes to:  
- 006_install_local_sites.md (the file you are reading)
- Your (new) proj-ha repo
- Your (new) proj-cg repo
- Your (new) proj-php repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```dev-setup-006-aa```  

### Download new site repos

1- Clone the ha lighting project repository from github  
- Github repo: https://github.com/debugacademy/proj-ha
- Place it where you want your website repo to reside
  - For example, I placed mine in: ~/Sites/haacademyvm

2- Clone the continuousgood project repository from github  
- Github repo: https://github.com/debugacademy/proj-cg
- Place it where you want your website repo to reside
  - For example, I placed mine in: ~/Sites/cgacademyvm

3- Clone the public_html project repository from github  
- Github repo: https://github.com/debugacademy/public_html
- Place it where you want your website repo to reside
  - For example, I placed mine in: ~/Sites/phpacademyvm

### Update local environment

4- Update your academyvm vagrant box's code  
- Pull in the latest updates from the academy vm repo (https://github.com/debugacademy/drupal-vm)
  - You should already have this repo as a remote in your academyvm folder
- Copy `example.config.yml` to `config.yml`.
  - **@Debug Academy:** These files do need to be cloned, but do not need to be modified at all.
- Edit `config.yml`, set (`local_path`, inside `vagrant_synced_folders`) to the directory you created for your sites to reside.
  - For example, I created: I will be using ~/Desktop/DebugAcademy/Sites
  - Edit *each* local_path variable appropriately. Just update paths from, for example, ~/Sites/haacademyvm, to the location your 'ha' repo reside$
- Open Terminal, cd to this directory (containing the `Vagrantfile` and this README file).
  - This is the directory named 'academyvm'
  - See 001_command_line_basics.md for information on how to cd
- Type in `vagrant reload`, and let Vagrant do its magic.
- Type in `vagrant provision`
- Edit your `.htaccess` file (```sudo nano /etc/hosts```), add the following entries:

```
193.169.88.88   academyvm.dev
193.169.88.88   ha.academyvm.dev
193.169.88.88   cg.academyvm.dev
193.169.88.88   php.academyvm.dev
```

### Install HA Lighting Drupal website

5- Install your HA Lighting website using the user interface
- Step 1: cd to your Vagrant box, then SSH in: 
  - `vagrant ssh`
- Step 2: Create MySQL database named `ha` in vagrant environment:
  - `mysql -uroot -proot -e 'create database ha;'`
    - You have created a database named 'ha', by using your MySQL username and password of 'root'.
- Step 3: copy sites/default/default.settings.php to sites/default/settings.php
- Step 4: edit sites/default/settings.php
  - Directly below the line `$databases = array();`, paste:
```
 $databases['default']['default'] = array(
   'driver' => 'mysql',
   'database' => 'databasename',
   'username' => 'username',
   'password' => 'password',
   'host' => 'localhost',
   'collation' => 'utf8_general_ci',
 );
```
- Step 5: Edit the section of code you just pasted to include the following:
  - Set the 'username' as 'root'
  - Set the 'password' as 'root'
  - Set the 'database' as the database name you used in Step 2
- Step 6: Follow the instructions shown at ha.academyvm.dev
  - Select the 'standard' profile
- Commit your updated settings.php file
- Submit a pull request to the site's repo with your updated settings.php file

### Install Continuous Good Drupal website

6- Install your ContinuousGood website using the user interface
- Step 1: cd to your Vagrant box, then SSH in: 
  - `vagrant ssh`
- Step 2: Create MySQL database named `cg` in vagrant environment:
  - `mysql -uroot -proot -e 'create database cg;'`
    - You have created a database named 'cg', by using your MySQL username and password of 'root'.
- Step 3: copy sites/default/default.settings.php to sites/default/settings.php
- Step 4: edit sites/default/settings.php
  - Directly below the line `$databases = array();`, paste:
```
 $databases['default']['default'] = array(
   'driver' => 'mysql',
   'database' => 'databasename',
   'username' => 'username',
   'password' => 'password',
   'host' => 'localhost',
   'collation' => 'utf8_general_ci',
 );
```
- Step 5: Edit the section of code you just pasted to include the following:
  - Set the 'username' as 'root'
  - Set the 'password' as 'root'
  - Set the 'database' as the database name you used in Step 2
- Step 6: run `drush site-install`
- Commit your updated settings.php file
- Submit a pull request to the site's repo with your updated settings.php file

### Create symlinks to DA repos
Follow the instructions in symlinks/README.md to create symlinks to each of the repos we use in class.

### Submit your assignment
You'll be submitting the following pull requests:  

#### This file
After following the instructions in symlinks/README.md:  
- `cd` to your da-assignments repository  
- `cd` to the symlinks folder inside of it  
- Run `ls -la` in the symlinks folder  
- Copy the information printed in the terminal  

Paste it here:  

**Pull request #1:** Submit a pull request containing what you pasted in this file.

#### HA Lighting repository
**Pull request #2:** Create a pull request containing the ha lighting settings.php file you created in class  
- The pull request should be to the ha lighting repository
  - https://github.com/debugacademy/proj-ha
- You'll need to fork the repository, then add your fork as a remote so you can push to it

#### Continuous Good repository
**Pull request #3:** Create a pull request containing the continuous good settings.php file you created in class  
- The pull request should be to the continuous good repository
  - https://github.com/debugacademy/proj-cg
- You'll need to fork the repository, then add your fork as a remote so you can push to it
