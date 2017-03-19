# Drupal site building
In this assignment, we will download a Drupal module that will allow us to add social media icons to our Portfolio Website.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your dev-1/proj-me directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Use the currently checked out branch in the proj-me repository**  

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

### Task 2 - Download and enable the module you chose
- Inside of vagrant ssh (var/www/dev-1/proj-me), run ```composer require drupal/MACHINE_NAME_OF_DRUPAL_MODULE_HERE```. This command will automatically download the module and place it into the proj-me/web/modules/contrib folder.  
- Next, you must log in to your Drupal website (`http://dev-1.academyvm.dev/proj-me/web`) . Click 'Extend' in the top administration bar. Select your module, and enable it.  

### Task 3 - Place the Social Media icons in the footer region of the website
- Visit your drupal site (`http://dev-1.academyvm.dev/proj-me/web`) and navigate to Structure » Block layout.
- If the module you are using comes with a block, place the block in the "Footer fifth" region and click on "Place block"
- Modify the social media icons and block appropriately (put your social media information for at least 3 accounts)
  - Feel free to use random usernames if you don't want to share yours.
- Save the block and click on "Save blocks" at the bottom of the Block Layout page
- Click on "Back to site" and you should see social media icons in the footer section of the website! Click on each one to verify they are going to the links you specified in the block configuration

### Task 3 - Export your website's configuration
- Create a new folder in your proj-me directory called "config". We will place all of our configuration exports in this folder from now on. 
- On your drupal site, navigate to Configuration » Configuration synchronization » Export. The full url will be 'http://dev-1.academyvm.dev/proj-me/web/admin/config/development/configuration/full/export'.
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the sites/dev-1/proj-me/config folder on your computer.
- Run git status to see which files have been added or modified
- Git add and commit the composer.lock and composer.json files in one commit
- Git add and commit the configuration file in your new config folder in another commit

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]).

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
