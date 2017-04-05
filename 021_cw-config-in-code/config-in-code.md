# Drupal site building
In this assignment, we will learn to export our drupal site's configuration using the command line as well as the features module.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your `/var/www/dev-1/proj-me` directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Use the currently checked out branch in the proj-me repository. This should be the branch that you created for assignments 12, 13, 14, or higher. Never work directly on the master branch.**  

To demonstrate the capability of configuration in code, we will make some unwanted changes to our drupal site and then undo those changes by running a drush command!

### Task 1 - Tell our website where to store our configuration
- First, we need to tell Drupal where to store configuration that we export. Using sublime text, open the settings.php file located inside proj-me/web/sites/default
- Delete the contents of line 767 (The line that starts with $config_directories) and replace it with the following:
```
$config_directories['sync'] = '../config/sync';
```
- That will tell your drupal site to store all exported configuration inside of the proj-me/config/sync folder.

### Task 2 - Export our website's configuration to code
- Let us export the current configuration of our site. Inside of vagrant, cd into /var/www/dev-1/proj-me/web
- Run ```drush cex```.
  - "drush" stands for "Drupal shell" and "cex" stands for configuration export.
- If done correctly, your terminal/gitbash will return a message such as "Configuration successfully exported to ../config/sync.".
- Run git status, you should see that files were added to your config/sync folder.
- Git add and commit the config/sync folder

### Task 3 - Change field labels on the "Portfolio" content type
- Navigate to Structure » Content types and next to the "Portfolio" content type, click on "Manage fields".
- Edit each of the fields and change the label to "DEBUGACADEMY". Be sure to save the fields.
- Look at your list of fields, confirm that the labels have been changed
- We've now made changes to our website's configuration, so our site configuration no longer matches the configuration we exported and committed

### Task 4 - Import (restore) your site's configuration
- Inside of vagrant, cd into /var/www/dev-1/proj-me/web.
- Run ```drush cim```. "drush" stands for "Drupal shell" and "cim" stands for configuration import.
- This will make your website read the configuration in your configuration files and implement it on your website
- Navigate to Structure » Content types and next to the "Portfolio" content type, click on "Manage fields". Read the field names.
- Your field names/labels should be back to what they were in the exported configuration! 
- This demonstrates how configuration in code can be used. You can always import your configuration from code to your website

### Task 5 - Use the features module to export the "Portfolio" content type.
Configuration export and import is great for exporting all of your site's configuration. But what if you simply wanted to share a content type from your site to a different website? The features module lets you export specific configuration into a custom module.

- Inside of vagrant, cd into /var/www/dev-1/proj-me/.
- Download the features module using composer. Run ```composer require drupal/features``` to download the features module.
- git add and commit your composer.json file in one commit, then git add and commit your composer.json file in another commit. Be sure these files are in separate commits - this is always done after downloading a module using composer. Your commit messages should say something descriptive along the lines of "Downloaded the features module - composer.json" and "Downloaded the features module - composer.lock".
- Inside of vagrant, cd into /var/www/dev-1/proj-me/web and run the command ```drush en features```. This is a handy drush command that will enable the features module as well as any dependencies that came with it.
- Navigate to Configuration -> Development -> Features -> +Create new feature
- Give the feature the name of "Portfolio Core".
- Under the "Content type" section on the right side, check the "Portfolio" content type
- Under the "View" section, check the "Portfolio" view
- Click on the "Write" button to automatically create/generate this a custom module (referred to as a 'feature' in this case) and it will be exported to proj-me/web/modules/custom
- Using your folder browser/finder on your computer, navigate to debugacademy/sites/dev-1/proj-me/web/modules/custom. You will see your newly created feature there. You have successfully created a Drupal Module! You can now share this module across other sites, and those sites will be able to get the "Portfolio" content type as well as the "Portfolio" view which we added to the feature
- Using the commandline and outside of vagrant, be sure to run git status to see which files or folders were added. Git add and commit your newly created feature.

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]).

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
