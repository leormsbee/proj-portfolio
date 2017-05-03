# Create a subtheme for the portfolio website
In this assignment, we will create a Drupal theme for our portfolio website.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the currently checked out branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-themes-029-aa```  

This work should be completed on your local proj-me website.  

### Task 1 - Download and install the latest version of the "Bootstrap" theme (https://www.drupal.org/project/bootstrap)
  - To do this, first SSH into your vagrant environment `vagrant ssh`
  - Then cd into the `proj-me` folder and run ```composer require drupal/bootstrap```.
  - The theme will automatically be downloaded to web/themes/contrib/
  - *Commit the addition of the "Bootstrap" theme in its own commit (composer.lock and composer.json files)*

### Task 2 - Create a subtheme
  - The following instructions were taken from Bootstrap's online documentation, which you can learn more about in the README.md file of the Bootstrap theme. We have gathered all the instrctions and pasted them here for your convenience.

  1 - Using your file finder, navigate to proj-me/web/themes/contrib/bootstrap/starterkits and copy the sass folder and paste it inside the proj-me/web/themes/custom folder.

  2 - Rename this newly pasted Sass folder to your site's name, followed by "theme". For example, proj_me_theme.

  3 - Rename the file name of the ```THEMENAME.libraries.yml``` file so that "THEMENAME" is replaced by your theme's machine name. For example: ```proj_me_theme.libraries.yml```.

  4 - Rename the title of the ```THEMENAME.starterkit.yml``` file so that "THEMENAME" is replaced by your theme's machine name and "starterkit" is replaced by info. For example, ```proj_me_theme.info.yml```.

  5 - Rename the title of the ```THEMENAME.theme``` file so that "THEMENAME" is replaced by your theme's machine name. For example, Ashraf would rename this file to ```proj_me_theme.theme```.

  6 - Using Sublime Text, open the file you renamed from step 5 and replace "THEMETITLE" with a name for your theme, such as 'Ashraf Theme'. In that same file, replace "THEMENAME" with your theme's machine name.

  7 - Navigate to config/install and replace the "THEMENAME" with your theme's machine name. Do the same for the file inside config/schema.

  8 - Inside vagrant ssh, navigate inside your proj-me folder, then run the following commands:
    - ```sudo gem install sass```
    - To verify that we successfully installed sass, run the following command: ```sass -v```. It should return something like: ```Sass 3.4.22 (Selective Steve)```. Congratulations! You've successfully installed Sass.

  9 - Navigate to proj-me/web/themes/custom/proj_me_theme and run the following command ```git clone https://github.com/twbs/bootstrap-sass.git bootstrap``` . This should place a folder named bootstrap inside of proj_me_theme

### Task 3 -  Enable your subtheme, then set it as your default theme  
  - To set the theme you just edited as the theme of your site, click 'Appearance' on your Drupal site and click "Install and set as default" under "mytheme".
  - When you visit your site's homepage, you might notice blocks all over the place. This is normal after enabling a theme for the first time.

### Task 4 - Make a noticeable SASS change to confirm your subtheme is working
  - Using Sublime Text, open the scss/_overrides.scss file and add the following to it:
```
body {
  background-color: red;
}
```
  - To compile SASS, use vagrant to cd to the your custom theme's folder folder then run ```sass --watch scss/style.scss:css/style.css```. If you did this correctly, you should see a new "css" folder inside your theme.
  - Clear your drupal site's cache by using vagrant to run "drush cr" from anywhere within the proj-me/web folder. The background of your Drupal site should now be red!
  - Outside of vagrant, commit all .scss and .css files that were modified. You can check this by running ```git status```.

### Task 5 - Refer to the design and begin theming!
1- Your homepage probably has blocks all over the place. This is normal when activating a new theme. Navigate to Structure » Block Layout and you can disable or remove the blocks you do not want displayed.  
2 - To Place your name on the top section of the website, place the "Site branding" block at the top of the Navigation region. To change this text, navigate to Configuration » Basic site settings and change the Site name to say your name. For the Site Slogan, add the following text: Digital Development & design that is built to last.
3 - Add the Portfolio, Blog, and Contact menu items by navigating to Structure » Menus and adding links to the "Main navigation". The contact menu item should link to your contact me page. The Portfolio menu item should link to your portfolio view that you created in a previous assignment. Lastly, the Blog menu item should link to your blog view that you created a while ago. **Note: You can point these links to the homepage for now and correct them later if you are unsure of the URLs.**
4 - Use the google inspector tool and Sass to align the menu items like they are aligned in the design. Remember to compile your sass when done by running ```sass --watch scss/style.scss:css/style.css``` from inside vagrant and within your custom theme's folder.
5 - Let us get rid of the logo that comes with Bootstrap. Navigate to Appearance » and click on settings next to your custom theme. Click on the Logo image tab at the bottom and uncheck the "Use the logo supplied by the theme" option. Remember to save the configuration.
## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]). The branch for this assignment was created in Task 2.

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
