# Create a subtheme for the portfolio website
In this assignment, we will create a Drupal theme for our portfolio website.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the develop branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-themes-026-aa```  

This work should be completed on your local proj-me website.  

Today's assignment will require NodeJS to be installed on our vagrant server. This particular theme requires Node.js to be installed. Node.js is an open-source, cross-platform JavaScript run-time environment for executing JavaScript code server-side. You do not need to know how to use nodejs to  build a theme.

0- To install NodeJS, use sublimetext to edit config.yml (which resides in academyvm). Replace the line:
`   # - nodejs`
with:
`   - nodejs`

Save your changes then run `vagrant provision` inside of your academyvm folder.

1- Download and install the latest version of the "Cog" theme (https://www.drupal.org/project/cog)
  - To do this, first SSH into your vagrant environment `vagrant ssh`
  - Then cd into the `proj-me` folder and run ```composer require drupal/cog```.
  - The theme will automatically be downloaded to web/themes/contrib/
  - *Commit the addition of the "Cog" theme in its own commit (composer.lock and composer.json files)*

2- Read the README.md from the "Cog" theme
  - Every base theme is different, so you must read the documentation in the "Cog" theme before starting. The README.md instructions file can be found at proj-me/web/themes/contrib/cog/README.md. This README file points us to Cog's documentation at this URL, use your browser to visit the URL: https://github.com/acquia-pso/cog/tree/8.x-1.x/STARTERKIT/README.md
  - The "Cog" theme has very thorough and valuable documentation

3- Create a subtheme
  - Follow the instructions in the "Create Cog Sub-Theme" section of the link you got from Task 2 ( https://github.com/acquia-pso/cog/tree/8.x-1.x/STARTERKIT/README.md ) to create the subtheme.
  - Commit the newly created 'mytheme' (composer.lock and composer.json files)

4- Enable your subtheme, then set it as your default theme  
  - To set the theme you just edited as the theme of your site, click 'Appearance' on your Drupal site and click "Install and set as default" under "mytheme".
  - When you visit your site's homepage, you might notice blocks all over the place. This is normal after enabling a theme for the first time.

5- Make a noticeable SASS change to confirm your subtheme is working
  - Follow all of the required steps to "Setup Local development" found in the Cog theme documentation (https://github.com/acquia-pso/cog/blob/8.x-1.x/STARTERKIT/README.md#setup-local-development). NOTE: These commands must be run inside vagrant ssh at /var/www/dev-1/proj-me
  - For example, make the background color red: 
```
body {
  background-color: red;
}
```
  - Using sublimetext, add that change to: 
    - proj-me/web/themes/custom/mytheme/sass/components/_header.scss (then compile the sass)
      - To compile SASS, cd to the mytheme folder then run ```gulp```
      - The background of your drupal site should now be red! You might have to clear the cache to see your changes.
  - Outside of vagrant, commit all .scss and .css files that were modified. You can check this by running ```git status```

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]). The branch for this assignment was created in Task 2.

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
