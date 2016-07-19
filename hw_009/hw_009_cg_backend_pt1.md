# Create module and features for Continuous Good, Part 1 (CG)
In this part of the assignment (part 1), we will create two features to export created content types to code.

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
Ashraf Abed would create a branch named: ```cg-backend-009-pt1-aa```

This work should be completed on your local CG website.  

### Install CG in dev-2 and stage-2
1- Follow instructions at https://github.com/debugacademy/course-drupal/blob/master/004_install_local_sites.md for installing Continuous Good, but in dev-2 (instead of dev-1):
  - Step-3 difference: DB command should now be `mysql -uroot -proot -e 'create database dev2_cg;'`
  - Step-7 difference: URL to install CG on dev-2: dev-2.academyvm.dev/proj-cg/install.php, db name is 'dev2_cg' (WARNING: If you fail to change the db name here, your dev1 database will be overwritten)

2- Repeat instructions above in stage-2:
  - Step-3 difference: DB command should now be `mysql -uroot -proot -e 'create database stage1_cg;'`
  - Step-7 difference: URL to install CG on stage-2: stage-2.academyvm.dev/proj-cg/install.php, db name is 'stage2_cg' (WARNING: If you fail to change the db name here, your dev1 database will be overwritten)

3- Add your fork as a remote in your proj-cg repo within dev-2 (this should be done within your VM at /var/www/dev-2/proj-cg)
  - If you have not already created a fork for the proj-cg repo in github, do so now.
  - `git remote add <nickname for your fork> <address for your fork>`

4- Rename origin remote to debugacademy:
  - `git remote rename origin debugacademy`

5- Repeat steps 3 and 4 within your stage-2 proj-cg repo.

### Starting from the same point
6- After reviewing all hw6 pull requests, we will be using Brandon's work as our starting point for exporting the site's content types to a feature:
  - From /var/www/dev-2/proj-cg, run the following commands:
    - `git remote add brandon https://github.com/bckesselly/proj-cg.git`
    - `git fetch --all`
    - `git checkout -b <branch name for this assignment> brandon/master`

7- In dev-2, enable the Backup and Migrate module (either from the user interface or via drush)
  - Clear the cache (`drush cc all`)
  - Go to admin/config/system/backup_migrate
  - Click on the "Restore" tab
  - Click "Choose File" under "Upload a Backup File" and select the cg-backup.mysql.gz file in this assignment's folder.
  - Click "Restore Now" at the bottom.

8- Download and enable the Features module in dev-2 (Do NOT commit this module, it has been committed into the debugacademy master branch).

### Review content types for familiarity
9- Login to your proj-cg site in dev-2, and go to admin > structure > Content Types:
  - Review the fields on the Organization and Cause content types

### Exporting content types to code
NOTE: Please refer to lecture on config in code for info on generating features (https://github.com/debugacademy/course-drupal/blob/master/055_config_in_code.md) for a good guide to supplement steps 10 and 11.

10- In dev-2, create cg_common_fields feature to export field bases to code:
  - Go to admin > structure > features, click Create new feature
  - Give the feature a title of CG Common Fields
  - Select all of the field bases needed to replicate the Organization and Cause content types (hint: If you are unsure, select "Organization" and "Cause" under content types - it should autoselect all of the field bases. In the end, make sure you uncheck everything aside from the components under field bases, dependencies, and taxonomy)
  - Click "Advanced Options" on the left side of the features page
  - In "Path to Generate feature module", enter 'sites/all/modules/custom'
  - Click "Generate feature"
  - Commit the cg_common_fields feature.
  - Enable the cg_common_fields feature:
    `drush en cg_common_fields -y`

11- Create cg_backend feature to export content types to code:
  - Create a new feature titled CG Backend
  - Select everything needed to replicate the organization and cause content types
  - You should notice that no field bases were included, and that instead the "CG Common Fields" module is listed under Dependencies. If you do not, try clearing caches and refreshing the create feature page.
  - Click "Advanced Options" on the left side of the features page
  - In "Path to Generate feature module", enter 'sites/all/modules/custom'
  - Click "Generate feature"
  - Commit the cg_backend feature.

### Submit a pull request
12 - Push your branch up to your Github fork for proj-cg and create a pull request.

### Test in your stage-2 environment
13- We will now "stage" your changes so that we can test them.
  - cd into `/var/www/stage-2/proj-cg`
  - `git fetch --all`
  - `git checkout -b <your branch name from step 12> <nickname for your fork from step 3>/<your branch name from step 12>`

14- Test your features:
  - `drush en cg_common_fields`
  - `drush en cg_backend`
  - Login to your proj-cg site in stage-2, and go to admin > structure > Content Types:
  - Review the fields on the Organization and Cause content types and verify that they match the fields on the Organization and Cause content types in dev-2
