# Drupal site building
In this assignment, we will begin building the structure for the Continuous Good content.

Note: lessons and presentations have been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment. They can be found here:
- Site building: https://github.com/debugacademy/course-drupal/blob/master/040_site_building.md
- Site building - specifics: https://github.com/debugacademy/course-drupal/blob/master/presentations/041_site_building.pdf

## Answering questions
For this assignment, you will be committing changes to:  
- hw_006_cg_site_building.md (the file you are reading)  
- The hw_006 folder

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

You will need contributed modules from drupal.org to complete this assignment. Don't be afraid to download and install a module to try it out to see if it fits your needs before. You can always disable and remove the module if it doesn't do what you're looking for.

#### Information to store on the Organization content type
*Note:* Although you should try to include most of these fields, there is some flexibility if you feel like there are other fields that should be here that are missing or if there are fields here that you think aren't relevant.
- Organization name
- Logo
- Cover photo (like facebook page cover photos)
- Location(s) (all addresses, if multiple are available)
  - Can divide this into multiple fields, if you feel that is better
- Description (long text and summary)
- Size (# of employees)
- Age (how many years it has been operating)
- Reputation (a number, out of 100)
- Reputation explanation (a long text field)
- Nonprofit (TRUE/FALSE, whether it is a nonprofit)
- (optional) percentage of donation that goes to causes
- Which causes the organization supports (entity reference)
- Website URL
- Relevant content (entity reference)

#### Information to store on the Cause content type
*Note:* Although you should try to include most of these fields, there is some flexibility if you feel like there are other fields that should be here that are missing or if there are fields here that you think aren't relevant.
- Cause name
- Description (long text and summary)
- Type of cause (poverty, war, homelessness, promotion)
- Verified (TRUE/FALSE, whether or not this cause is legit)
- Location(s)
- Cover photo
- Number of people affected
- Relevant content (entity reference)
- ? (suggestions are welcome)

#### Question 1:
*Describe five fields and their field types you used to create your content types.*
*Place your answer here.*

#### Question 2:
*List the contributed modules you used and what you used them for.*
*Place your answer here.*

### Task 2 - Export your work using the backup and migrate module

- Download the Backup and Migrate module from drupal.org.
- Enable the module (either from the user interface or via drush).
- Go to admin/config/system/backup_migrate
- Click "Backup Now"
- Move the exported file to the hw_006 directory (the directory this file is in)
- Commit the exported file in its own commit

#### Submitting your assignment
Submit a *single* pull request with Questions 1 and 2 answered, as well as the export of your work from Task 2.
