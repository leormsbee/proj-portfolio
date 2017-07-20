# Using Composer with Drupal
In this assignment, we will learn about composer and install a Drupal 8 website.  

## Answering Tasks
For this assignment, you will be committing changes to:  
- (new repository) debugacademy/htdocs/dev-1/proj-portfolio/  

Or the *equivalent* path on our virtualmachine:  
- /var/www/dev-1/proj-portfolio  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

**Windows users: Always run git bash as administrator.**

## Tasks
Task 1 - Clone our new project
- Visit https://github.com/debugacademy/proj-portfolio
- Click 'Clone or download', then copy the URL (should be `https://github.com/debugacademy/proj-portfolio.git`)
- cd into our debugacademy/htdocs/dev-1 folder
- Clone the repository: `git clone [Paste git clone URL. should end in .git]`

Task 2 - Fork our new project's repository  
- Visit https://github.com/debugacademy/proj-portfolio  
- Press 'Fork' in the upper right corner  
- Click 'Clone or download', then copy the fork's URL  
- cd into our recently cloned repository: `cd ~/Desktop/debugacademy/htdocs/dev-1/proj-portfolio`  
- Add your fork as a remote  
- Create a new branch in our site project for this assignment, named composer-010-[your initials].  

Task 3 - Use composer to download site files  
- cd into academyvm and run ```vagrant up```  
- SSH into vagrant: ```vagrant ssh```  
- cd into our site: `cd /var/www/dev-1/proj-portfolio`  
- Run `ls -la` to confirm the presence of a file named composer.json  
- Run `composer install` . It will automatically read the file composer.json and download all of the listed files.  
  - Note: Windows users may experience lag and permissions issues  
    - In case of permissions issues, we have a work-around you can use. Inform the instructor.  

Task 4 - Commit composer.lock
After running `composer install` successfully, composer.lock will be generated.  
- Git add and commit the updated file composer.lock  

Task 5 - Install our Drupal website
- Visit dev-1.academyvm.dev/proj-portfolio/web
- Go through the installation steps
- For the database credentials, fill in these values:
  - db name: dev1_portfolio
  - db username: root
  - db password: root
- Continue through all of the installation steps
- **Remember the username and password you choose for your website.**

Task 6 - Add a new module using composer
- SSH into vagrant (cd into academyvm, run vagrant ssh)
- cd into your website: `cd /var/www/dev-1/proj-portfolio`
- Download an additional module (package) using the composer require command:
  - composer require drupal/admin_toolbar:^1
- Git add and commit the composer.json file
- *Then* git add and commit the composer.lock file

Task 7 - Enable the new module
- Log in to your Drupal website at dev-1.academyvm.dev/proj-portfolio/web/user/login
- Use the username and password you chose during site installation
- Move your mouse over the 'Structure' menu link. Notice there is *no* dropdown.
- Press 'Extend' in the top row of links
- Check the checkbox next to 'Admin Toolbar'
- Scroll to the bottom of the page and press 'Install'
- Visit the homepage of your website
- Move your mouse over the 'Structure' menu link. Notice there *is* a dropdown.
- We've installed the module successfully!

Task 8 - Create a brand new Drupal project using composer
In Task 1, we cloned an existing project from github. This time, we will generate a new one from the drupal community's composer drupal project template.  

- cd into /var/www/dev-1  
- Run the command: `composer create-project drupal-composer/drupal-project:8.x-dev personal-project --stability dev --no-interaction`  
- cd into the new folder `personal-project`
- Run `ls -la` to confirm the presence of a file named composer.json  
- Run `composer install` . It will automatically read the file composer.json and download all of the listed files.  
  - Note: Windows users may experience lag and permissions issues  
    - In case of permissions issues, we have a work-around you can use. Inform the instructor.  
- Repeat tasks 4, 5, 6, and 7 in the new project's folder (i.e. replace proj-portfolio with personal-project in the instructions)  

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-portfolio repository (e.g. git push [remote-name] composer-010-[your initials]).

### Step 2
Create a pull request to the proj-portfolio repository on github. Once you visit the main proj-portfolio repository on github (https://github.com/debugacademy/proj-portfolio), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).

