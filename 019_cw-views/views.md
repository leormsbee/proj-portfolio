# Drupal site building
In this assignment, we will create views to list content of different content types.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your `/var/www/dev-1/proj-me` directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Use the currently checked out branch in the proj-me repository**  

### Task 1 - Ensure your website has Portfolio and Blog content types
For this assignment, we will be listing Portfolio items and Blog posts. You should have created these content types as part of class work #13 and homework #14, respectively. You can check to see if your website has these content types by navigating to Structure » Content types. If you do not have them, let the learning assistant know and he will provide you with instructions so that you can participate in this assignment. 

### Task 2 - Create the "Portfolios" view
- Navigate to Structure » Views. Click on "+Add view".
- Name it "Portfolio" and select show Content of the "Portfolio" type. Under "PAGE SETTINGS", check the box next to "Create a page".
- The page title should be "Portfolio" and the path should be just "portfolio", the same way it is automatically filled in for you.
- Make it so that 4 items are displayed instead of 10 and uncheck the box next to "Use a pager". Click on "Save & edit".
- On the View configuration page and under "FORMAT", click on "Content" and select "Fields" instead of content. Click "Apply" until you get back to the configuration page.
- We have now successfully set up a view where we can add fields of the "Portfolio" content type. Let us begin adding fields!
- The "Content: Title" field is automatically added by the view. This field will show the "Title" of the content type that you specified earlier in this task.
- Add the "Picture" field to the view. Click on "Add" and search for "Picture". Verify that you are adding the "Picture" field from the Portfolio content type by reading the description of the field. It will tell you that it "Appears in: portfolio" which tells us that this field is used by our "Portfolio" content type. Select the field and click on "Add and configure fields". Use the "Large" Image style and click on "Apply".
- Save the view and navigate to http://dev-1.academyvm.dev/proj-me/web/portfolios to see your view. If you did it correctly, you should see titles as well as pictures underneath them. You have successfully created a page that lists content!

### Task 3 - Create the "Blog Posts" view
- Navigate to Structure » Views. Click on "+Add view".
- Give it a name of "Blog Posts" and have it show Content of the "Blog" type. Under "PAGE SETTIONS", check the box next to "Create a page".
- The page title should be "Blog Posts" and the path should be just "blogs".
- Make it so that 3 items are displayed instead of 10 and uncheck the box next to "Use a pager". Click on "Save & edit".
- On the View configuration page and under "FORMAT", click on "Content" and select "Fields" instead of content. Click "Apply" until you get back to the configuration page.
- We have now successfully set up a view where we can add fields of the "Blog" content type. Let us begin adding fields!
- The "Content: Title" field is automatically added by the view. This field will show the "Title" of the content type that you specified earlier in this task.
- Add the "Authored on" field to the view. This field will give us the date that the blog post was created on. Click on "Add" and search for "Authored on". As you will see under the description, this field shows "The time that the node was created". Select the field and click on "Add and configure fields". Under "Date format", choose the "HTML Date format".
- Save the view and navigate to http://dev-1.academyvm.dev/proj-me/web/blog to see your view. If you did it correctly, you should see blog titles as well as the date the blogs were created on. You have successfully created another page that lists content!

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
