# Drupal site building
In this assignment, we will download a Drupal module that will allow us to add social media icons to our Portfolio Website.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-portfolio repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your dev-1/proj-portfolio directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the develop branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```socialm-013-aa```

### Task 1 - Research which Drupal 8 module to use for placing social media icons
Our site will feature social media icons, such as twitter, linkedin, facebook, etc. on every page of the website. Instead of changing our design's code to include the social media icons, it would be preferable to find a Drupal module that makes selecting icons and setting URLs for them easier.
- Search google for a Drupal 8 module which provides this functionality. The modules you find should all be located on drupal.org. 
Module must have a Drupal 8 version
To determine which module is best, compare things like: 
- How many downloads the module has
- How stable is the D8 version (dev, alpha, beta, full release)
- How many D8 bugs does the module have (in the issue queue)
- When was the module last updated

Record the 'machine name' of the module. It is the module name from the drupal.org URL - the portion of the URL *after* drupal.org/project/

### Task 2 - Download the module you chose
- Inside of vagrant ssh (var/www/dev-1/proj-portfolio), run ```composer require drupal/MACHINE_NAME_OF_DRUPAL_MODULE_HERE```. This command will automatically download the module and place it into the proj-portfolio/web/modules/contrib folder.  
- Now that the module's code is placed in our website's codebase, we should commit the module's addition to our website:  
  - git add and commit the composer.json file with a proper commit message  
  - git add and commit the composer.lock file with a proper commit message  

### Task 3 - Enable the module
- Next, you must log in to your Drupal website (`http://dev-1.academyvm.dev/proj-portfolio/web`) . Click 'Extend' in the top administration bar. Select your module, and enable it.  
- Note: Alternatively, you could have enabled your module using `drush en [modulename]`  

### Task 4 - Place the Social Media icons in the footer region of the website  
- Visit your drupal site (`http://dev-1.academyvm.dev/proj-portfolio/web`)  
- If the module you are using comes with a block, navigate to Structure » Block layout, then continue these instructions  
  - If it does NOT come with a block, read the module's documentation and experiment to determine how to use it.  
- Place the block in the "Footer fifth" region and click on "Place block"
- Enter random (placeholder) social media information for at least 3 accounts
- Save the block and click on "Save blocks" at the bottom of the Block Layout page
- Click on "Back to site" and you should see social media icons in the footer section of the website! Click on each one to verify they are going to the links you specified in the block configuration

### Task 5 - Export your website's configuration
- Navigate to Configuration » Configuration synchronization » Export
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the 013_cw_site-building directory on your computer (the directory this file is in)
- Run git status to see the new file
- Run git add to add the file
- Commit this file

## Submitting your assignment

### Step 1
Push the branch(ES) you created for this assignment to your fork of the proj-portfolio and da-assignments repositories (e.g. git push [remote-name] [branch name]).  

**Because one file is committed to da-assignments, and others are committed in proj-portfolio, you must create two pull requests for this assignment.**  

### Step 2
Create a pull request to the proj-portfolio repositiory on github. Once you visit the main proj-portfolio repository on github (https://github.com/debugacademy/proj-portfolio), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).  
