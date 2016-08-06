# Create module and features for Continuous Good, Part 2 (CG)
In this part of the assignment, we will create the main module for the CG codebase.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-cg repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
**Create a branch based off of the proj-cg master branch using the following convention:**
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cg-backend-009-pt2-aa```

This work should be completed on your local CG website.  

1- Make sure your new branch in your proj-cg repo is based off of the LATEST master.
  - `git fetch --all`
  - `git checkout -b <branch_name_for_this_assignment> debugacademy/master`

### Creating a custom module
2- Create a module titled cg_main:
  - Create a folder with the name cg_main inside of sites/all/modules/custom
  - Create a new file titled cg_main.module inside of the cg_main folder
  - Add an opening php tag (`<?php`) to the module and a new line right under it (i.e. hit return on your keyboard after the php tag)
  - DO NOT add a closing php tag (Including the closing tag may cause strange runtime issues on certain server setups.)
  - Commit your work.

3- Tell Drupal about the module:
  - Create a new file titled cg_main.info inside of the cg_main folder
  - Add the following to the .info file:

  ```
  name = Continuous Good Main
  description = For custom CG code and updates
  core = 7.x
  ```
  - Commit your work.

4- If all was done correctly, your module should now appear in the module list in your site (Note: if it does not, check for issues like accidentally creating module files with .txt at the end, e.g. cg_main.info.txt instead of just cg_main.info).

### Adding an install file
5- Add an install file with an implementation of hook_enable:
  - Create a new php file titled cg_main.install inside of the cg_main folder with the following content:

  ```
  <?php

  /**
   * @file
   * Hooks and enable code for Continuous Good.
   */

  /**
   * Implements hook_enable().
   */
  function cg_main_enable() {

  }

  ```
  - Commit your work.

6- Research how to enable a theme and make it the default using php in Drupal, then add code to enable our cg_theme and set it as the default in the enable hook from step 5 above.
  - Commit your work.

7- Research how to enable a module using php in Drupal, then add code to enable our cg_pages feature (remember, exported feature are really just modules) in the enable hook from step 5 above.
  - Commit your work.

### Testing our work
8- Test that your new custom module works:
  - If you have cg_pages enabled, disable it (`drush dis cg_pages`).
  - If cg_theme is currently your default theme, set a different theme to be your default theme (e.g. Bartik or Zen).
  - Clear caches: `drush cc all`
  - Enable the cg_main module: `drush en cg_main`
  - Verify that cg_pages is enabled and that cg_theme is set as the default theme.

### Submit a pull request
9 - Push your branch up to your Github fork for proj-cg and create a pull request.
