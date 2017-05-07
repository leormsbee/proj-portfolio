# Continue theming the design for the portfolio website
In this assignment, we will continue theming our portfolio website.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

This work should be completed on your local proj-me website.  

### Task 0 - Initial Website set up
Throughout the semester we've been working individually on our projects. Today, we will merge in work from a teammate, and use that as our starting point. Future classwork and homework assignments by team members will also be merged in.

#### Export your work
After running vagrant up, `ssh` into vagrant.
`cd` into your proj-me/web folder (`cd /var/www/dev-1/proj-me/web`)
Export all of your site's config: `drush config-export`

Outside of vagrant, `cd` to your proj-me folder.
Create a new branch to save your previous work on: `git checkout -b my-progress`
Add and commit everything you just exported to your new branch: `git add --all && git commit -m 'Full site export'`

Find the alias of the Debug Academy account: `git remote -v` . We will act like it is "debugacademy" for the following steps.
Delete your local develop branch, if one is present: `git branch -D develop` It is OK if it says branch does not exist.
Create a new develop branch based off of Debug Academy's:
- `git fetch debugacademy`  
- `git checkout -b develop debugacademy/develop`  

SSH back into vagrant and cd into your proj-me folder.
Download any modules/themes that are on develop but not on your site: `composer install`
Still in vagrant, `cd` into the proj-me/web folder: `cd web`
Re-install your site: `drush site-install -y`
Set the same unique site ID as is used in the develop branch's config:
`drush cset system.site uuid 0003034d-1229-4224-8de0-7deb6a4c2f39`
To get around a bug in Drupal core, run the following:
`drush ev '\Drupal::entityManager()->getStorage("shortcut_set")->load("default")->delete();';`
Import your new site configuration: `drush config-import`

You should now have the same exact site set up as your entire class. Create a new branch for this assignment!

## Questions
**Create a branch based off of the currently checked out branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-theming-030-aa```  


### Task 1 - Style the menu items to match the design
- This involves applying sass and then compiling it
- To compile SASS, use vagrant to cd to the your custom theme's folder folder then run ```sass --watch scss/style.scss:css/style.css```.
- Use the google inspector tool to see which selectors you should apply styling to

### Task 2 - Place the social media icons block next to the menu items
- This can be done by going to Structure » Block layout
- Add sass as necessary to ensure correct placement according to the design

### Task 3 - Code the hero section, hero text, and the call to action button
- To do this, we will need to edit a custom twig template file.
- Copy the proj-me/web/themes/contrib/bootstrap/templates/system/page.html.twig file and paste it into proj-me/web/themes/custom/proj_me_theme/templates
- Rename this template file to page--front.html.twig so that it will only target the front page
- You will need to add html to this file to create the hero section. This includes using the div, h2, and a elements. You will need to apply a background image to the div that you create. Copy the hero.jpg image from the da-assignments/030_cw-theming folder to proj-me/web/themes/custom/proj_me_theme/images so that your theme has access to it.

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]). The branch for this assignment was created in Task 2.

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
