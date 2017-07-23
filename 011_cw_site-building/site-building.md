# Drupal site building
In this assignment, we will begin building the structure for our Portfolio Website, which is our semester's project.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local da-assignments repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, open a new Command Line window/tab and cd into debugacademy/sites/dev-1/da-assignments to commit changes to this assignment.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```site-building-011-aa```  

### Step 0
You must be logged in to your local Drupal 8 website to complete these tasks. The URL should be: http://dev-1.academyvm.dev/proj-portfolio/web 

### Task 1 - Set up the "Technologies" Taxonomy Vocabulary.
Goal: Give your site the use of organizational keywords, also known as categories or tags. "Taxonomy" is Drupal's way of categorizing content.
- Navigate to Structure » Taxonomy » +Add Vocabulary
- Give it a name of "Technologies" (no need to fill out the description).
- Click on "+Add Term". 
- Give it the name of "Drupal" and click on save (no need to fill out description or URL alias).
- Repeat this and create a term for each of the following:
	- Drupal
	- Drupal 7
	- Drupal 8
	- Composer
	- Git
	- HTML
	- CSS
	- SASS
	- PHP

- To verify which terms you created, navigate to Structure » Taxonomy » and click on list terms to the right of "Technologies". **You should have a total of 9 terms**.

### Task 2 - Set up the portfolio content type
Goal: Set up the infrastructure for storing portfolio content and its features on the portfolio website. 

#### Information (fields) to store on the Portfolio content type:
*Note:* Although you should try to include these fields, there is some 'business' flexibility. If you feel like there are other fields that should be here that are missing, or if there are fields here that you think aren't relevant, simply let us know which on slack and we can decide whether a different field makes more sense. 

- Navigate to Structure » Content types » Add content type. The url should be `http://dev-1.academyvm.dev/proj-portfolio/web/admin/structure/types/add'
- Give this content type the name of 'Portfolio' and a Machine-readable name of 'portfolio' (Machine-readable names should always be in lowercase). You do not need to fill out a description. Click on "Save and manage fields"

The "Title" field automatically comes with any content type that you create, so we do not manually create it.

Click "Edit" next to the existing "Body" field:
- Change the "Label" from Body to Description
- Make the field "required"
- Save your changes

Click on "+ Add field" to add the "Image" field:
- Type: Image
- Label: Picture
- You do not need to fill out any other settings for this field
- Save your changes
- You can verify you created this field by going to Structure » Content types » Portfolio > Manage fields

Click on "+ Add field" to add the "Technologies" field:
- Type: Taxonomy term
- Label: Technologies
- Make it so that the allowed number of values is unlimited
- Under "Available Vocabularies", check the "Technologies" checkbox. This will allow users to select terms from the Taxonomy type "Technologies"
- Save the field
- You can verify you created this field by going to Structure » Content types » Portfolio > Manage fields
- Go to "Manage form Display" (a tab next to "Manage fields") and change the Technologies Widget from Autocomplete to Check boxes/radio buttons.
- Save your changes

### Task 3 - Create 3 pieces of content!
- Navigate to Content » +Add Content » Portfolio
- Fill in the title of a "testing" portfolio item
- Fill in a sentence or two for a description 
- Select at least 3 "Technologies". These values are being derived from the "Technology" vocabulary we created. How cool is that!
- Add any image. Add a one word description for the "Alternative text" field.
- Save your changes
- Repeat this 2 more times so that you have 3 total pieces of content for the "Portfolio" Content type.
- You can view all the content you created by clicking on "Content" in the top administration bar.

### Task 4 - Export your website's configuration
- Navigate to Configuration » Configuration synchronization » Export
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the da-assignments/011_cw_site-building directory on your computer (the directory this file is in)
- Run git status to see the new file
- Run git add to add the file
- Commit this file

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] site-building-011-[your initials]).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the main da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
