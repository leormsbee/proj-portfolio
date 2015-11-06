# Drupal site building
In this assignment, we will begin preparing to build HA Lighting.  

Note: a lesson has been posted in the da-lessons repository on Drupal site building. It contains relevant information to this assignment. It can be found here: https://github.com/debugacademy/da-lessons/blob/master/040_site_building.md

## Answering questions
For this assignment, you will be committing changes to:  
- 007_contrib_download.md (the file you are reading)  
- Your halighting repo  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```ha-setup-006-aa```  

### Question 1
Download (and enable) the latest stable Drupal 7 versions of the following modules, *and their dependencies*, if any:  
- `features`: drupal.org/project/features  
- `views`: drupal.org/project/views  

Place the modules in the following directory:  
- `[your-ha-repository]/sites/all/modules/contrib`  

Pro-Tip: When you enable a module using drush, it gives you the option of auto-downloading the module's dependencies.  

### Question 2
Download (and enable) the latest stable Drupal 7 versions of the following theme, *and its dependencies*, if any:  
- `zen`: drupal.org/project/zen  

Place the theme folder in the following directory:  
- `[your-ha-repository]/sites/all/themes/`  

Pro-Tip: When you enable a theme using drush, it gives you the option of auto-downloading the module's dependencies.  

### Question 3

Edit this file, and describe the steps you took to download and enable the modules, themes, and their dependencies.  

Place your answer here.  

### Pull requests
Submit 1 pull request with the new modules to your *HA repository*, but **place each module in its own commit!**  

Submit another pull request with the changes you've made to this file to your da-assignments repository.  
