# Classwork - Creating a View.
In this classwork assignment, we will use Drupal to create a View that will contain a list of themes. We will then place the view on the homepage using the panels module.

## Answering questions
For this assignment, you will be committing changes to:  
- Your proj-themes repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Tasks
**Continue to use the same branch as your most recent site building work was done on**  


Task 1 - Create 4 nodes of the Theme content type. This can be done by navigating to Content » Add Content » Theme. Fill in all the fields and save the nodes. You can verify how many "Themes" you created by clicking on the "Content" tab in the admin bar.

NOTE: You will need to make sure the CMS Compatibility Taxonomy has a few terms listed. You can add terms to this by navigating to Structure » Taxonomy and then adding the terms (Drupal 7 , Drupal 8, Wordpress, etc.) to a taxonomy. When creating your theme nodes, you should see a checkbox widget under the "CMS Compatibility" field with the options I mentioned above.

**You might have already downloaded some of the modules in the following tasks. If so, simply move on to the next step.**

Task 2 - Use drush to download and enable the Views and Ctools modules (https://www.drupal.org/project/views) and (https://www.drupal.org/project/ctools).  
This can be done by using the command line to navigate to your proj-themes repository and running ```drush en views ctools -y```. As always after downloading modules, git add and commit them in their own commits. You will also need to enable the Views UI (views_ui) and Views content panes (views_content) modules. These two module are included as part of the Views and Ctools modules. You can verify that all the necessary modules are enabled by visiting the modules section of your drupal site. 

Task 3 - Create a new view by going to Structure » Views » Add new view. 
 - The view name should be "Featured Themes" 
 - Next to **Show**, select *Content*.
   - Change type of content shown from all to *Theme*
 - Check the "Create a page" checkbox, give it an appropriate title and path, and have it display 3 items.
 - Press *Continue & Edit*
 - On the next page under Format, change it to **Show:** *Fields* instead of content
 - Under **Fields**, click the + Add button. You will then need to add the following fields to the view:
   - Title
   - Desktop image
   - CMS Compatiblity
   - Link to the theme. (Search for Content: Link). Hide the label of this field and enter "More Details" in the "Text to display" field
 - Under "Displays", click the + Add button and add a content pane and save the view The view should now have two displays, "Page" and "Content Pane"
 
Task 4 - We will now use the panels module to place this view on the homepage.
 - Use drush to download and enable the "panels" module
 - Enable the "Page manager" (page_manager) module
 - Visit Structure » Pages
 - Create a new panel page 
 - We will now create the homepage panel page. This panel page will allow us to place different drupal components on the homepage, such as blocks, views, custom text, etc.
 - Give this new panel page the title of homepage and check the box that says "Make this your site home page."
 - Give it a path of /index
 - Continue until you reach the "Panel content" page. Set the title to "No title", and click on the gear in the top left corner of the "Center" rectangle 
 - Click on Add Content » View panes and select the view you just created. This will add that view to our homepage panel
 - Click on finish and "Update and Save" to save your changes
 - You should now see a view on the homepage listing 3 themes and the fields mentioned above!

Task 5 - Add your newly created view and panel page to the Athemes core feature, then generate that feature and git add/commit it.

Task 6 - Stage the content on your staging environment.
If you have not done so already, you must first install your proj-themes website **in your stage-1 environment**. This means repeating the proj-themes installation steps from this lesson ( https://github.com/debugacademy/da-assignments/blob/master/cw_002_site_install/cw_002_site_install.md#download-new-site-repos ),  but replacing dev-1 with stage-1 in each step.

Once your staging website is installed, stage your work on your staging website. This means following steps 1-5 on this lesson: https://github.com/debugacademy/course-drupal/blob/master/lessons/057_staging_updates.md#1-reset-the-staging-environment

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
