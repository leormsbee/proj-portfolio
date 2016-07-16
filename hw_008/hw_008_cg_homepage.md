# Create homepage for Continuous Good (CG)
In this assignment, we will create and style the homepage for CG. This assignment makes heavy use of the features module and custom content panes.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-cg repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the proj-cg master branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cg-home-008-aa```  

This work should be completed on your local CG website.  

1- Make sure your new branch in your proj-cg repo is based off of the LATEST master. There are updates there that will bring in a new feature titled cg_pages. This feature provides a starting point for the homepage.

2- Enable the cg_pages feature:
  - `drush en cg_pages -y`
  - This should enable the cg_pages feature and all of the moduels it depends on.

3- Visit the homepage. You should now see it is updated with new content. Yes, it is very bare - you're going to fill in the rest!

4- The homepage as it stands is a panels page with one custom content pane.
  - To complete the homepage, you will need to add the remaining custom panes and style them appropriately.
  - To add a custom pane, go to admin > structure > Custom content panes and click "+Add" on the top of the page. From there you will be able to give your pane a Category, Title, and Body (HTML). I gave the first pane a Category of "Homepage". You can do the same.
  - You can also add and rearrange custom panes simply by clicking "Customize this page" from the homepage.

5- As you add and rearrange custom content panes on the homepage, you will cause your feature to take on a status of 'Overridden.' Because of this (and to keep our changes in version controlled using Git) you should be re-exporting the cg_pages feature with the updates you make:
  - For example, if I were to add a custom content pane titled "Malik-123" to the homepage, I would go to admin > structure > features > Continuous Good Pages > Recreate.
  - I would then find the Malik-123 pane under "Custom Content Panes" on the right side of Features wizard, and check the checkbox indicating I'd like to include it in the feature.
  - Click "Advanced Options" on the left side, and click Generate Features.
  - In terminal or Git bash, if you type `git status`, you should see that modifications were made to the cg_pages feature. Commit these changes often (e.g. Exported Malik-123 pane to cg_pages feature).
  - NOTE: When you turn in this assignment via pull request, if your cg_pages feature has a status of Overridden, what you turn in will differ from what you have saved on your local environment.

6- Your styling changes should be done within cg_theme by writing SASS and compiling it into CSS using `bundle exec compass compile` or `bundle exec compass watch`. Add images that you need to the images folder in your cg_theme and make sure to commit them. The src path for these images will be `"/sites/all/themes/cg_theme/images/<image_name>.jpg"`.
