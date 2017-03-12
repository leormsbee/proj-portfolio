# Using Composer with Drupal
In this assignment, we will learn about composer and install a Drupal 8 website.  

## Answering Tasks
For this assignment, you will be committing changes to:  
- (new repository) sites/dev-1/proj-me/  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
Task 1 - Fork our new project's repository
- Visit https://github.com/debugacademy/proj-me
- Press 'Fork' in the upper right corner

Task 2 - Clone our new project
- Visit your fork of our site's repository
- Click 'Clone or download', then copy the URL (should be `https://github.com/[YOUR USERNAME]/proj-me.git`)
- cd into our sites/dev-1 folder
- Clone the repository: `git clone [Paste git clone URL. should end in .git]`
- cd into our newly cloned repository: `cd proj-me`
- Add the debugacademy account as a remote: `git remote add debuga https://github.com/debugacademy/proj-me.git
- Create a new branch in our site project for today's work, named composer-cw-012-[your initials].

Task 3 - Use composer to download site files
- cd into academyvm and run ```vagrant up```
- SSH into vagrant: ```vagrant ssh```
- cd into our site: `cd /var/www/dev-1/proj-me`
- Run `ls -la` to confirm the presence of a file named composer.json
- Run `composer install` . It will automatically read the file composer.json and download all of the listed files.

Task 4 - Commit composer.lock
After running composer install successfully, composer.lock will be generated. 
- Exit your vagrant environment: `exit`
- cd into your project's folder sites/dev-1/proj-me
- Git add and commit the file composer.lock

Task 5 - Install our Drupal website
- Visit dev-1.academyvm.dev/proj-me/web
- Go through the installation steps
- For the database credentials, fill in these values:
  - db name: dev1_me
  - db username: root
  - db password: root
- Continue through all of the installation steps
- **Remember the username and password you choose for your website.**

Task 6 - Add a new module using composer
- SSH into vagrant (cd into academyvm, run vagrant ssh)
- cd into your website: `cd /var/www/dev-1/proj-me`
- Download an additional module (package) using the composer require command:
  - composer require drupal/admin_toolbar:^1
- Git add and commit both the composer.json and composer.lock files

Task 7 - Enable the new module
- Log in to your Drupal website at dev-1.academyvm.dev/proj-me/web/user/login
- Use the username and password you chose during site installation
- Move your mouse over the 'Structure' menu link. Notice there is *no* dropdown.
- Press 'Extend' in the top row of links
- Check the checkbox next to 'Admin Toolbar'
- Scroll to the bottom of the page and press 'Install'
- Visit the homepage of your website
- Move your mouse over the 'Structure' menu link. Notice there *is* a dropdown.
- We've installed the module successfully!

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] composer-cw-012-[your initials]).

### Step 2
Create a pull request to the proj-me repository on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).

