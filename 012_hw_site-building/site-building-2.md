# Drupal site building
In this assignment, we will continue building the structure for our Portfolio Website.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local da-assignments repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, open a new Command Line window/tab and cd to debugacademy/sites/dev-1/da-assignments.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```site-building-012-aa```  

### Task 1 - Create the Blog content type
Goal: Set up the infrastructure for storing Blog content and its features on the portfolio website. 

#### Information (fields) to store on the Blog content type:

- Navigate to Structure » Content types » Add content type. The url should be `http://dev-1.academyvm.dev/proj-portfolio/web/admin/structure/types/add'
- Give this content type the name of 'Blog'. You do not need to fill out a description. Click on "Save and manage fields"

The "Title" field automatically comes with any content type that you create, so do not have to manually create it.

Click on "+ Add field" to add the "Author" field:
- Type: Text (plain)
- Label: Blog Author
- It should only have one value
- Make it a required field
- Save the field
- You can verify you created this field by going to Structure » Content types » Blog > Manage fields

Edit the existing Body field:
- Make it a required field
- Save the field

Click on "+ Add field" to add the "Blog Image" field:
- Type: Image
- Label: Blog Image
- You do not need to fill out any other settings for this field
- Save the field
- You can verify you created this field by going to Structure » Content types » Blog > Manage fields

### Task 2 - Create 3 pieces of content!
- Navigate to Content » +Add Content » Blog
- Fill in the title
- Fill in a sentence or two for the Blog Body. 
- Add any image. Add a one word description for the "Alternative text" field.
- Save your content
- Repeat this 2 more times so that you have 3 total pieces of content for the "Blog" Content type.
- You can view all the content you created by clicking on "Content" in the top administration bar.

### Task 3 - Export your website's configuration
- Navigate to Configuration » Configuration synchronization » Export
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the 012_hw_site-building directory on your computer (the directory this file is in)
- Run git status to see the new file
- Run git add to add the file
- Commit this file

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] site-building-012-[your initials]).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the main da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
