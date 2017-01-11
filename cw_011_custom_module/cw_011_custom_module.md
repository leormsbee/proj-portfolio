# Create a custom module for the Academy Themes website
In this assignment, we will create a custom Drupal module for our Academy Themes website. This module, once enabled, will automatically enable our Athemes theme and set it as the default theme. It will also be a placeholder for future development work.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-themes repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the develop branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-themes-011-aa```  

This work should be completed on your local proj-themes website.

1 - Navigate to the appearance section of your site using the user interface and disable the Athemes theme if you already have it enabled. Enable and set as default the bartik theme. 

2 - Create a folder for our custom module named athemes, place it inside your proj-themes/sites/all/modules/custom directory. You can use the ```mkdir``` command to create the folder. The folder name matches the name of your module, as is standard practice. Every custom module needs at least two files, a [MODULENAME]`.info` file and a [MODULENAME]`.module` file. You can also create a [MODULENAME]`.install` file which will run code anytime the module is installed, enabled, disabled, uninstalled, or updates are run. Let us go ahead and create the .info file:

- cd into your athemes custom module folder and use the ```touch``` command to create a file called athemes.info. Any file inside of a custom module should have the prefix of the module name. You can do this by running ```touch athemes.info```.
- Inside this athemes.info file, add then edit the following code:
```
name = Replace this sentence with the name you chose for this custom module
description = Replace this sentence with a short description of what this module does.
core = 7.x This field explains the version of Drupal that your module is for. Delete this sentence, ONLY keep core = 7.x on this line
```
- There are many more properties that you can assign to a .info file, as detailed in the Drupal documentation (https://www.drupal.org/docs/7/creating-custom-modules/writing-module-info-files-drupal-7x). One common example is `dependencies[] = modulename`, as a way of requiring other modules to be enabled before yours can. We won't be using that command today. The ones in the code block above are all we need for now. Save the .info file and commit it.

3 - In the athemes custom module, create a .module file using the ```touch``` command. This file will be called athemes.module. For now, this file will simply contain an opening php tag: `<?php` followed by a blank line. Do not close the php tag. Commit this file.

4 - In the athemes custom module, create a .install file using the ```touch``` command. This file will be called athemes.install.
- Inside this file, start with an opening php tag followed by a blank line. Do not close the opening php tag.
- Create a function that takes no parameters called hook_enable. Replace "hook" with the name of this module. 
- Inside this function, we will create the code that will enable our theme and set it as the default theme. Inside the function, create a variable named $theme and set it equal to the our theme's machine name (because it's a string, the theme name should be placed inside single quotes).
- Research how to programmatically enable a theme and set it as default in drupal 7.
- Use that code to enable our custom theme within our athemes_enable() function. Be sure to substitute our custom theme's machine name in the answer you find.
- After that, let us disable any enabled themes. In this case, we will disable the bartik theme. Use the ```theme_disable``` function to create an array with the name of the theme that you want to disable inside. For example: ```function(array('replace_this_with_theme_we_want_to_disable!'));```
- Commit this file

5 - Go to your proj-themes site and navigate to the modules section using the user interface. You should see our newly created Athemes module! Run ```drush en athemes``` and watch the magic happen. 

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
