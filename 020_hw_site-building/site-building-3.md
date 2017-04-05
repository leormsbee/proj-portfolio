# Drupal site building
In this assignment, we will create a content type, pieces of content, as well as a view to list content of the content type we created.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your `/var/www/dev-1/proj-me` directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Use the currently checked out branch in the proj-me repository**  

### Task 1 - Create the "Reference" content type
Goal: Set up a content type that you can fill in with professional references. If you have a professional reference/review from a supervisor or a manager, you can display it on your website to show potential employers.

#### Information (fields) to store on the "Reference" content type:
- Navigate to Structure » Content types » Add content type. 
- Give this content type the name of 'Reference'. You can fill out a very brief description. Click on "Save and manage fields"

The "Title" field automatically comes with any content type that you create, so you do not have to manually create it. Change the label from "Title" to "Author" on the create/edit content type page (not on the add fields page).

Click on "+ Add field" to add the "Organization" field:
- This field will be used to record the organization/company of the person giving you a reference
- Type: Text (plain)
- Label: Organization
- It should only have one value
- Make it a required field
- Save the field
- You can verify you created this field by going to Structure » Content types » Blog > Manage fields

Edit the existing Body field:
- Make it a required field
- Save the field

Click on "+ Add field" to add the "Reference Image" field:
- This field will be used to display an image of the person giving you a reference or their company
- Type: Image
- Label: Reference Image
- You do not need to fill out any other settings for this field
- Save the field
- You can verify you created this field by going to Structure » Content types » Reference > Manage fields

### Task 2 - Create 3 pieces of content!
- Navigate to Content » +Add Content » Reference
- Fill in the title
- Fill in a name for the Reference Author
- Fill in a name for the Organization field
- Fill in a sentence or two for the Reference Body. 
- Add any image. Add a one word description for the "Alternative text" field.
- Save your content
- Repeat this 2 more times so that you have 3 total pieces of content for the "Reference" Content type.
- You can view all the content you created by clicking on "Content" in the top administration bar.

### Task 3 - Create the "References" view
- Navigate to Structure » Views. Click on "+Add view".
- Give it a name of "References" and have it show Content of the "Reference" type. Under "PAGE SETTINGS", check the box next to "Create a page".
- The page title should be "References" and the path should be just "references", the same way it is automatically filled in for you.
- Ensure that the "Use a pager" box is checked and you have 10 filled in under "Items to display". Click on "Save & edit".
- On the View configuration page and under "FORMAT", click on "Content" and select "Fields" instead of content. Click "Apply" until you get back to the configuration page.
- We have now successfully set up a view where we can add fields of the "Reference" content type. Let us begin adding fields!
- The "Content: Title" field is automatically added by the view. This field will show the "Title" of the content type that you specified earlier in this task.
- Under the "FIELDS" section of the view, click on Add to add a field. Add the "Reference Author" field to the view.
- Add the "Organization" field to the view.
- Add the "Reference Image" field to the view. Click on "Add" and search for "Reference Image". Select the field and click on "Add and configure fields". Use the "Large" Image style and click on "Apply".
- Save the view and navigate to http://dev-1.academyvm.dev/proj-me/web/references to see your view. If you did it correctly, you should see some of the references that you created. This includes their titles, author, organization, and picture. You have successfully created a page that lists content using the views module!

### Task 4 - Export your website's configuration
- You should already have a folder in your proj-me directory called "config". As mentioned in previous assignments, this is where we will place all of our configuration exports. 
- On your drupal site, navigate to Configuration » Configuration synchronization » Export. The full url will be 'http://dev-1.academyvm.dev/proj-me/web/admin/config/development/configuration/full/export'.
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the sites/dev-1/proj-me/config folder on your computer.
- Outside of vagrant, Run git status to see which files have been added or modified
- Outside of vagrant, Git add and commit the composer.lock and composer.json files in one commit
- Outside of vagrant, Git add and commit the configuration file in your new config folder in another commit

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]).

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
