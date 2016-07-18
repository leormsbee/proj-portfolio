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

### Install CG in dev-2
1- Follow instructions at https://github.com/debugacademy/course-drupal/blob/master/004_install_local_sites.md for installing Continuous Good, but in dev-2 (instead of dev-1):
  - Step-3 difference: DB command should now be `mysql -uroot -proot -e 'create database dev2_cg;'`
  - Step-7 difference: URL to install CG on dev2: dev-2.academyvm.dev/proj-cg/install.php, db name is 'dev2_cg'

2- Add your fork as a remote in your proj-cg repo within dev-2 (this should be done within your VM at /var/www/dev-2/proj-cg)
  - If you have not already created a fork for the proj-cg repo in github, do so now.
  - `git remote add <nickname for your fork> <address for your fork>

3- Rename origin remote to debugacademy:
  - `git remote rename origin debugacademy`

### Starting from the same point
4- After reviewing all hw6 pull requests, we will be using Jonathan's work as our starting point for exporting the site's content types to a feature:
  - `git remote add jonathan https://github.com/Barthe941/proj-cg.git`
  - `git fetch jonathan`
  - `git checkout -b <branch name for this assignment> jonathan/master`

5- Enable the Backup and Migrate module (either from the user interface or via drush)
  - Clear the cache (`drush cc all`)
  - Go to admin/config/system/backup_migrate
  - Click on the "Restore" tab
  - Click "Choose File" under "Upload a Backup File" and select the cg-backup.mysql.gz file in this assignment's folder.
  - Click "Restore Now" at the bottom.

6- Download and enable the Features module (Do NOT commit this module, it has been committed into the debugacademy master branch).

### Review content types for familiarity
7- Go to admin > structure > Content Types:
  - Review the fields on the Organization and Cause content types

### Exporting content types to code
NOTE: Please refer to lecture on config in code for info on generating features (https://github.com/debugacademy/course-drupal/blob/master/055_config_in_code.md) for a good guide to supplement steps 7 and 8.

8- Create cg_backend feature to export content types to code:
  - Go to admin > structure > features, click Create new feature
  - Give the feature a title of CG Backend
  - Select everything needed to replicate the organization and cause content types
  - Uncheck all field bases (keep the field instances, we will store field bases in a seprate feature named cg_common_fields)
  - <Insert module generation instructions>
  - Commit the cg_backend feature.

9- Create cg_common_fields feature to export field bases to code:
  - Create a new feature titled CG Common Fields
  - Select everything needed to replicate the organization and cause content types
  - This time, uncheck everything EXCEPT for the field bases
  - <Insert module generation instructions>
  - Commit the cg_common_fields feature.

### Submit a pull request
10 - Push your branch up to your Github fork for proj-cg and create a pull request.
