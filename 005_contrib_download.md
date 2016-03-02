# Drupal site building
In this assignment, we will begin building ARCS and DebugAcademy.com.  

Note: a lesson has been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment.  

## Answering questions
For this assignment, you will be committing changes to:  
- 005_contrib_download.md (the file you are reading)  
- Your proj-arcs repo  
- Your proj-debugacademy repo  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Project]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```arcs-006-aa```  

### Question 1
Download the latest stable Drupal 7 versions of the following modules:  
- `features`: drupal.org/project/features  
- `views`: drupal.org/project/views  
- `views_slideshow`: www.drupal.org/project/views_slideshow
- `panels`: drupal.org/project/panels  
- `date`: drupal.org/project/date  

Place the modules in the following directory:  
- `[your-arcs-repository]/sites/all/modules/contrib`  

### Question 2
Enable each of the the modules you downloaded using drush.  

#### To use drush:
1. `cd` to your vagrant box (the academyvm folder)  
2. Run `vagrant ssh`  
Now we are connected to our Virtual machine. Let's `cd` to our repositories; on our virtual machine, they are located in `/var/www`.

1. Go to the folder /var/www: `cd /var/www`
2. Use the `ls` command to see your repositories
3. Use the `cd` command to enter your website's repository. e.g. `cd proj-arcs`, or `cd /var/www/proj-arcs`

Now we are on our virtual machine, in our website's folder. That means we can use drush!
- Use `drush dl [module's machine name]` to download modules
  - If you are unsure of your module's machine name, it is usually the module name in the drupal.org project page's URL  
- Use `drush en [module's machine name]` to enable modules

Pro-Tip: When you enable a module using drush, it gives you the option of auto-downloading most or all of the module's dependencies.  

### Question 2
Download (and enable) the latest stable Drupal 7 versions of the following theme, *and its dependencies*, if any:  
- `zen`: drupal.org/project/zen  

Place the theme folder in the following directory:  
- `[your-arcs-repository]/sites/all/themes/`  

Pro-Tip: When you enable a theme using drush, it gives you the option of auto-downloading the module's dependencies.  

### Question 3
We want to add all of these same modules to our debug academy website. Repeat this entire assignment, but adjust instructions for the proj-debugacademy repository.  

### Question 4
Edit this file, and briefly describe the steps you took to download and enable the modules, themes, and their dependencies.  

Place your answer here.  

### Pull requests
Submit 1 pull request with the new modules to your *proj-arcs repository*, but **place each module in its own commit!**  

Submit another pull request with the changes you've made to this file to your da-assignments repository.  
