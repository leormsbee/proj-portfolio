# Drupal site building
In this assignment, we will learn to export our drupal site's configuration from one environment (or site) to another.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review. 

### Task 1 - Create a staging website in stage-1 (if you have not already done so)
**If you had problems running composer install (mostly Windows users), do not follow these steps. Contact the learning assistant instead.**
1. cd into academyvm, run `vagrant ssh`
2. `cd` into `/var/www/dev-1/proj-me`
3. Run `git remote -v`. Copy only the URL to your fork (the one with your github username in it)
4. `cd` into /var/www/stage-1
5. Run `git clone [URL YOU COPIED] proj-me`
6. `cd` into `/var/www/stage-1/proj-me` . Run `composer install`
7. Install your site at stage-1.academyvm.dev/proj-me/web/
  - **Name your database stage1_dev** . DB Username and password are both `root`

### Task 2 - Give your staging site the same UUID as your dev site
- In order to share configuration between two environments/sites, drupal requires those two environments/sites to have the same UUID (Unique ID). Currently, your dev-1/proj-me site has a different unique ID than your stage-1/proj-me site. Let us make them both have the same UUID.
  - Using your terminal/gitbash, vagrant ssh, then cd into `/var/www/dev-1/proj-me` and run the following command: ```drush cget system.site uuid```. Copy the ID that is returned
  - Next, cd into your staging website `/var/www/stage-1/proj-me` and run the following command: ```drush cset system.site uuid ID-THAT-YOU-JUST-COPIED```
Now your dev and staging sites have the same Unique Site ID! Now they are able to use the same configuration as each other.

### Task 3 - Create a branch for the work we are staging
- `cd` into `/var/www/dev-1/proj-me`
- Create a new branch for staging: `staging-04-09-17-[YOUR-INITIALS]`
- Export all configuration: `drush cex`
- Commit all of your work. Run `git status` to see what needs to be committed, if anything.

### Task 4 - Checkout the staging branch on your staging site
We want to be able to pull code from our dev site to our staging site, so we should add our dev site as a remote to our staging site.
- `cd` into your staging site: `cd /var/www/stage-1/proj-me`  
- Add your dev-1 environment as a remote using a relative path: `git remote add dev1 ../../dev-1/proj-me/.git`  
Now, we want to checkout the staging branch we just created:
- This will download all branches from our dev environment: `git fetch dev1`  
- Now, checkout the staging branch we created: `git checkout -t dev1/staging-04-09-17-[YOUR-INITIALS]`
Lastly, run `composer install` to download all files according to what we committed in our staging branch's composer files

### Task 5 - Import the configuration into your staging website
Before we can import our configuration, we need to tell our website where our configuration is.
- Edit the file debugacademy/sites/stage-1/proj-me/web/sites/default/settings.php
- Add this line to the *very* bottom of your settings.php file: `$config_directories['sync'] = '../config/sync';`
- That will tell your drupal site to store and look for all exported configuration inside of the proj-me/config/sync folder.

Now, let's import our config!
- Inside of `/var/www/stage-1/proj-me` , run `drush cim` .
This should import all of the configuration that you have exported on your dev environment.

### Task 6 - Confirm your branch contains what you expect it to
Now, log in to your staging website at stage-1.academyvm.dev/proj-me/web/
And ensure the work you did on your dev site is also present on your staging website. If it is, you have successfully staged your work!

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]). The branch for this assignment was created in Task 2.

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
