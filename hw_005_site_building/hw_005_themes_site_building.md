# Drupal site building
In this assignment, we will begin building the structure for the Theme website content.

Note: lessons and presentations have been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment. They can be found here:
- Site building: https://github.com/debugacademy/course-drupal/blob/master/040_site_building.md
- Site building - specifics: https://github.com/debugacademy/course-drupal/blob/master/presentations/041_site_building.pdf

## Answering questions
For this assignment, you will be committing changes to:  
- hw_005_themes_site_building.md (the file you are reading)
- The hw_005_site_building folder
- Your local proj-themes repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```themes-005-aa```  

### Task 1 - Set up Theme and Theme Purchase content types
Goal: Set up the infrastructure for storing themes and their features on the portfolio website.  

Free and paid Themes will be listed on the website. Users will be able to choose which themes to download for free or which themes to purchase then download.  

We will create separate content types for Theme and Theme Purchases.  

You will need contributed modules from drupal.org to complete this assignment. Don't be afraid to download and install a module to try it out before finalizing your decision and determining if it fits your needs. You can always disable and delete the field then remove the module if it doesn't do what you're looking for. *Every downloaded moduled from drupal.org should be placed in proj-themes/sites/all/modules/contrib*. You may need to manually create the 'contrib' directory first.  

#### Information (fields) to store on the Theme content type:
*Note:* Although you should try to include these fields, there is some 'business' flexibility. If you feel like there are other fields that should be here that are missing, or if there are fields here that you think aren't relevant, simply let us know which on slack and we can decide whether a different field makes more sense. *Multiple field types will be unavailable OOTB (out of the box) and are provided by modules from Drupal.org, where you will need to find them*.  
Navigate to Home » Administration » Structure » Content types. The url should be `[your-site-URL]`/admin/structure/types/add  
- Desktop image of the theme (image field)
  - Allows multiple values
- Tablet image of the theme (image field)
  - Allows multiple values
- Mobile image of the theme (image field)
  - Allows multiple values
- Price of theme (Decimal or Float field)
- Whether the theme is free or paid (Boolean field)
- Whether the theme is featured or not (Boolean field)
- Whether the theme is responsive or not (Boolean field)
- URL for the live demo (Text field)
- Username for the live demo (Text field)
- Password for the live demo (Text field)
- A list of features that the theme provides (Text List field with unlimited values)
- Which CMS's the theme is compatible with. i.e. drupal 7, drupal 8, wordpress, etc. (Taxonomy reference field)
- Files included (List field of text, multiple values allowed)
- Link to the user that created the theme (Entity Reference field allowing user selection)
- A Zip file of the theme (File field)  

##### Additional features for the content type:  
- Users should be able to rate themes out of 5 stars
- Users should be able to ask questions (leave comments) on each theme

#### Information (fields) to store on the Theme Purchase content type:
- The theme being purchased (EntityReference field to the theme content type)
- Which theme package is being purchased i.e whether single use or unlimited use. (List field of text)
- E-mail address of the purchaser (Email field)
- User account of the purchaser (Entity reference to user)

### Task 2 - Add an "Author" user role:
Navigate to Home » Administration » People » Permissions. The url should be `[your-site-URL]`/admin/people/permissions/roles  
- First name (Text field)
- Last name (Text field)
- Picture (Image field)
- Short description of themselves (Long Text field)
- URL to their linkedin (Text field)
- Phone number. (Text Field)
- Email address. (Email Field)
- Testimonial (Long Text field). We will eventually show this on the homepage or “Meet the graduates” section

#### Question 1:
*Describe the field types used for creating the following fields in your content types:*
- Desktop image of the theme (Theme content type): Answer here
- Whether the theme is free or paid (Theme content type): Answer here
- A Zip file of the theme (Theme content type): Answer here
- The theme being purchased (Theme Purchase content type): Answer here

#### Question 2:
*List the contributed modules that you needed to download for your field types, and which fields you used them for.* Tip: You can use git to see which modules you added to the codebase.
*Place your answer here.*

### Task 3 - Export your website's database using the backup and migrate module
- Download the Backup and Migrate module from drupal.org, place it in your website's sites/all/modules/contrib folder.
- Enable the module (either from the user interface or via drush).
- Clear the cache (drush cc all)
- Go to admin/config/system/backup_migrate
- Click "Backup Now"
- Move the exported file to the hw_005_site_building directory (the directory this file is in)
- Commit the exported file in its own commit

#### Submitting your assignment - This file
Submit a *single* pull request with Questions 1 and 2 answered, as well as the export of your work from Task 3, to the da-assignments repository.

### Task 4 - Submit the modules you added to your website using a pull request (PR)
- cd to your proj-themes repository
- One by one, add and then commit *every* module that you enabled on your website for this assignment
- Each module should be in its own commit. A sample commit message is "Added the entityreference module".

#### Submitting your assignment - Website work
- Push your branch from your proj-themes repository to your proj-themes fork (Fork the repository if you have not done so yet)
- Submit a single pull request through the proj-themes repository, which should include every module downloaded to complete this assignment.
