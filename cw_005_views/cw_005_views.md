# Classwork - Creating a View.
In this classwork assignment, we will use Drupal to create a View that will contain a list of users. We will then place the view on a page using the panels module.

## Answering questions
For this assignment, you will be committing changes to:  
- Your proj-themes repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Tasks
**Continue to use the same branch as your most recent site building work was done on**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```views-cw-005-aa```

Task 1 - Create 4 users. This can be done by navigating to `People » Add User`. Fill in all the fields and save the user. You will then need to go back to the users list and edit the newly created users so you can fill in all the fields you created as part of the Author role during a previous assignment (hw_005_site_building). This includes filling in the following fields for each user:
- User name
- User Picture
- LinkedIn URL  
* If you are not up to date on homework, simply fill in the fields that are available on the user profile.  

Task 2 - Create a new theme by visiting `Content » + Add content » Theme`. In the "Link to the user that created the theme" field, select all four users that you just created. By doing this, your theme is now "referencing" the 4 users you just created.

NOTE: The "Link to the user that created the theme" field from homework 5 should be of the widget type "Check boxes/radio buttons". This will allow you to select users more easily. The field setting should also allow unlimited values, rather than the default of 1.  

Task 3 - Use drush to download and enable the Views and Ctools modules (https://www.drupal.org/project/views) and (https://www.drupal.org/project/ctools).  
This can be done by using the command line to navigate to your proj-themes repository and running ```drush en views ctools -y```. As always after downloading modules, git add and commit them in their own commits. You will also need to enable the Views UI (views_ui) and Views content panes (views_content) modules. These two module are included as part of the Views and Ctools modules. You can verify that all the necessary modules are enabled by visiting the modules section of your drupal site. 

Task 4 - Create a new view by going to Structure » Views » Add new view. 
 - The view name should be "Theme Developers" 
 - Next to **Show**, select *Users*.
 - Uncheck the checkbox that says Create page
 - Press *Continue & Edit*
 - Under **Fields**, click the + Add button. You will then need to add the following fields to the view:
   - User's name
   - User Picture
   - LinkedIn URL

 - Expand the "Advanced" link on the right side and click to Add a relationship. Select the Entity Reference: Referencing entity relationship. 
 - Add a contextual filter and search for and select 'Content: Nid'.  
   - For Content: Nid's settings, under *WHEN THE FILTER VALUE IS NOT AVAILABLE*, choose `Display contents of "No results found"`
   - Apply/Save the filter
 - Enable the module Views Content Panes (`views_content`).
 - Under "Displays", click the + Add button and add a content pane and save the view. The view should now have a display of "Content Pane". 
 - **Save the view**.

Task 5 - We will now use the panels module to place this view on every theme node.
 - Use drush to download and enable the panels module
 - Enable the "Page manager" (page_manager) module
 - Visit Structure » Pages
 - Enable the Node template (`node/%`) page. This panel page will allow us to lay out our node pages using the panels module, which allows us to place different drupal components on our nodes such as blocks, views, custom text, etc.
 - Edit the Node template page.  
 - Create a new variant named 'Theme', and check the box **Selection Rules**. Press Continue once.
 - Using the dropdown with item 'Context exists', select *Node:type*, then choose theme. This ensures this layout will only be used for theme nodes. 
 - Continue through the steps until you reach the "Panel content" page.
 - Click on "Create a new Variant" so that it is saved. 
 
 - Click on the gear icon in the top left corner of the rectangle labeled "Center". 
 - Click on Add Content » View panes and select the view you just created. This will add that view to our Node panel.
 - Click on finish and "Update and Save" to save your changes
 - When visiting a theme that you created, you should now see the view that you created!

Task 6 - Add your newly created view and panel page to the Athemes core feature, then generate that feature and git add/commit it.

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
