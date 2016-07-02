# Drupal site building
In this assignment, we will begin building the structure for the Continuous Good content.

Note: lessons and presentations have been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment. They can be found here:
- Site building: https://github.com/debugacademy/course-drupal/blob/master/040_site_building.md
- Site building - specifics: https://github.com/debugacademy/course-drupal/blob/master/presentations/041_site_building.pdf

## Answering questions
For this assignment, you will be committing changes to:  
- hw_006_cg_site_building.md (the file you are reading)  
- The hw_006 folder
- Your local continuous good repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cg-ctype-06-aa```  

### Task 1 - Set up Organization and Cause content types
Goal: Set up the infrastructure for storing organizations and their causes on the continuous good website.

Organizations (such as the red cross) will be listed on the continuous good website. Users will be able to choose to support specific organizations.

Furthermore, causes will be listed on the website. For example, the Syrian refugee crisis is a cause.

Organizations can fundraise for specific causes.

Many organizations can fundraise for the same cause.

Organizations should link to the causes they support.

We will create separate content types for organizations and causes.

You will need contributed modules from drupal.org to complete this assignment. Don't be afraid to download and install a module to try it out before finalizing your decision and determining if it fits your needs. You can always disable and delete the field then remove the module if it doesn't do what you're looking for. *Every downloaded moduled from drupal.org should be placed in proj-cg/sites/all/modules/contrib*. You may need to manually create the 'contrib' directory first.

#### Information to store on the Organization content type
*Note:* Although you should try to include these fields, there is some 'business' flexibility. If you feel like there are other fields that should be here that are missing, or if there are fields here that you think aren't relevant, simply let us know which on slack and we can decide whether a different field makes more sense. *Multiple field types will be unavailable OOTB (out of the box) and will need to be downloaded from Drupal.org*.
- Organization name (text)
- Logo (image)
- Cover photo (like facebook page cover photos, large image)
- Location(s) (all addresses, if multiple are available)
  - Can divide this into multiple fields, if you feel that is better
  - Must use a field type which allows plotting locations on a map
- Description (long text and summary)
- Size (# of employees - integer)
- Age (how many years it has been operating - integer)
- Expert Rating (a number, out of 100)
- Rating explanation (a long text field)
- Community Rating (out of 5 stars)
- Nonprofit (TRUE/FALSE {boolean} whether it is a nonprofit)
- Percentage of donation that goes to causes (float)
- Which causes the organization supports (entity reference pointing to the Cause content type)
  - This field must be added *after* the Cause content type is created
- Website URL (link)
- Related content (entity reference to any content type)
- Additional fields? (suggestions are welcome)

#### Information to store on the Cause content type
*Note:* Although you should try to include these fields, there is some 'business' flexibility. If you feel like there are other fields that should be here that are missing, or if there are fields here that you think aren't relevant, simply let us know which on slack and we can decide whether a different field makes more sense. *Multiple field types will be unavailable OOTB (out of the box) and will need to be downloaded from Drupal.org*.
- Cause name
- Description (long text and summary)
- Type of cause (taxonomy field, default options including: poverty, homelessness, promotion, domestic abuse)
- Verified (TRUE/FALSE, whether or not this cause has been verified by our team)
- Location(s) (all addresses, if multiple are available)
  - Must use a field type which allows plotting locations on a map
- Cover photo
- Number of people affected
  - Use a list (integer) field
  - Make 'range' options, such as:
    - key: 1, label: 0 - 10.
    - key: 11, label: 11-50.
    - key: 51, label: 51-100. 
    - key: 101, label: 100+. 
- Relevant content (entity reference to any content type)
- Additional fields? (suggestions are welcome)

#### Question 1:
*Describe the following fields and their field types which you used to create create them for your content types:*
- Location field (organizations): Answer here
- Cover photo field (organizations): Answer here
- Expert rating field (organizations): Answer here
- Community rating field (organizations): Answer here

#### Question 2:
*List the contributed modules that you needed to download for your field types, and which fields you used them for.* Tip: You can use git to see which modules you added to the codebase.
*Place your answer here.*

### Task 2 - Export your website's database using the backup and migrate module
- Download the Backup and Migrate module from drupal.org, place it in your website's sites/all/modules/contrib folder.
- Enable the module (either from the user interface or via drush).
- Clear the cache (drush cc all)
- Go to admin/config/system/backup_migrate
- Click "Backup Now"
- Move the exported file to the hw_006 directory (the directory this file is in)
- Commit the exported file in its own commit

#### Submitting your assignment
Submit a *single* pull request with Questions 1 and 2 answered, as well as the export of your work from Task 2.

### Task 3 - Submit the modules you added to your website using a pull request (PR)
- cd to your continuous good repository
- Add then commit *every* module that you enabled on your website for this assignment
- Each module should be in its own commit

#### Submitting your assignment
- Push your work to your continuousgood fork (or Fork the repository if you have not done so yet)
- Submit a single pull request through the continuous good repository, which should include every module downloaded to complete this assignment.
