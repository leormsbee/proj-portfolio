# Classwork - Team site development, Newsletter block
In this classwork assignment, we will use Drupal to create a newsletter block that will allow users to sign up for our newsletter. We will then need to place that newsletter block on the homepage using the panels module.

## Answering questions
For this assignment, you will be committing changes to:  
- Your proj-themes repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Tasks
### Task 1 - Create a Back up of your development website's current status
- Backup your site's database by getting a database dump using the Backup and Migrate module.
  - Enable the module: `drush en backup_migrate -y`
  - Visit the path 'admin/config/system/backup_migrate' while logged in as user 1. Here is a shortcut: `drush uli 1 admin/config/system/backup_migrate`
  - Press **Backup Now**
  - Create a folder named backups in proj-themes/sites/default/files. For example `cd proj-themes/sites/default/files` then `mkdir backups`
  - It is recommended to move the backup file you downloaded into your sites/default/files/private folder, and to rename it using the following format: `[nameofyourbranch]`-`[todaysdate]`, and keep the file extension unchanged. This file will serve as a backup if we ever need to restore previous copy of the website.
- Commit any work in progress to your current branch
- Backup your site's code using a git tag
  - `git tag branchname-todaysdate`
  - Your code is now backed up on a 'tag', which is similar to a branch, except that it cannot be updated. It is a snapshot of code at a specific period in time.
  
### Task 2 - Re-install your development website using the latest code
The goal here is to update your local environment to exactly match the *develop* branch from the site's primary github repository.

Now that your code and database are backed up (Task 1), we can safely delete the data in our database.

First, we will update our code (master and develop branches) to match that of production:
- Pull down the latest changes from the **develop branch**. 
  - `git checkout master`
  - `git fetch [remote alias for the live site's code]` 
    - The alias is often 'origin' or 'da'. Use `git remote -v` to verify, if not sure. For the following instructions we will assume the alias is *origin*.
  - `git reset origin/master --hard`
  - Your master branch is now reset to match production.
- Create your develop branch if you have not already done so: `git checkout -b develop`
  - If the branch was previously created, simply run: `git checkout develop`
- Pull the latest work to your development branch from production: `git pull origin develop`  
Your develop and master branches now match those on production exactly.

- Create a new branch for this work based off of the updated develop branch.
  - `git checkout -b cw-007-your-initials develop`

Now we can install our new website with the up-to-date code.
- Empty your database. This can be done using drush via the ```drush sql-drop -y``` command. You must be in your proj-themes repo and ssh'ed into the server for this to work. This cannot be undone, which is why we performed Task 1 (backing up our work). 
- Install your site again by running the drush command ```drush site-install```
- Enable the Athemes Core feature ```drush en athemes_core -y```

**We should now have a freshly installed site that functionally is up-to-date (matches) our production website's develop branch.**

### Task 3 - Download and enable a Drupal module that will create a newsletter email input block, as shown in the homepage design.
- The block should have an input field where users can type in their email address, along with a submit button.
- The module should allow for the placement of the newsletter block on a panel page. Place this newsletter block on the home panel page.
- Add this block to the athemes core feature and commit it.

NOTE: Protoyping can be faster than researching. It might be faster to download and experiment with a few Drupal newsletter modules as opposed to spending a lot of time researching the exact functionality you are seeking.

When this is complete, update the appropriate features (Athemes Core and/or Athemes Field Bases).

### Task 4 - Create a "Featured Free Theme" view.
- Make sure that your site has at least two themes with all the fields filled in, and that the boolean fields "Featured theme" and "Free theme" are checked.
- This view will only show one theme.
- The view should only show a theme that is featured and free (this will involve adding filter criteria to the view).
- When finished adding fields and filters to the view, add a "Content Pane" display to the view
  - Save the view
- Edit the homepage panel page (found on `admin/structure/pages`)
- Place the created view on the homepage panel page.
- Recreate the Athemes Core feature to include the view you created
- Commit your updates.

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
