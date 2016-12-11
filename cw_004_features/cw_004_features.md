# Classwork - Creating Features
In this classwork assignment, we will use Drupal to create features that will contain our content types and contact form.

## Answering questions
For this assignment, you will be committing changes to:  
- Your proj-themes repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Complete this classwork assignment on the same branch as your first site building homework assignment:**  

### Download and enable the features module.
After ssh'ing into vagrant, cd into your proj-themes site and then run `drush en -y features`.

### Create the "Athemes Core" feature.
Log in to your website, then navigate to Home » Administration » Structure » Features - Create Feature

This feature will ultimately contain all site configuration aside from field bases. Initially, it will contain all the content types you created as part of the previous assignment, as well as the contact form we built in class. 
- Name this feature "Athemes Core".
- Expand "CONTENT TYPES" on the right side and check off the content types that you created.
- Find the Contact Form and check it off.
- **Uncheck** *all* "Field Bases". Field bases should never be included in this feature.
- Under "ADVANCED OPTIONS", click on "Generate feature". This will export the feature and place it inside sites/all/modules
- Use git to add and commit this feature.

### Create the "Athemes Field Bases" feature.
Log in to your website, then navigate to Home » Administration » Structure » Features - Create Feature

This feature will contain only the field bases of the fields belonging to the content types you created
- Name this feature "Athemes Field Bases".
- Expand "FIELD BASES" on the right side and check off all the field bases relating to the fields you created as part of the previous assignments.
- Under "ADVANCED OPTIONS", click on "Generate feature". This will export the feature and place it inside sites/all/modules
- Use git to add and commit this feature.

#### Create a pull request
To submit this assignment, create a pull request which will contain the features module, as well as the two features you just created.  

By submitting this pull request which includes the two features, you have effectively re-submitted your previous site building homework assignment without needing to submit a database export. The features include the content types, entityform, and fields needed to re-create your site.
