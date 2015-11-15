# Drupal site building
In this assignment, we will export and deploy the public-facing pages of HA Lighting.  

## Answering questions
For this assignment, you will be committing changes to:  
- 010_export_ha_public_pages.md (the file you are reading)  
- Your halighting repo (you should be able to access it using the shortcut at symlinks/halighting)

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```ha-export-010-aa```  

### Export structure for public pages
Goal: Submit a pull request containing at least all modules, content types and views for deploying the HA public pages you created as part of assignment 008.

You will use the Features module, as well as any addon modules required, for exporting the content types, views, and others.

#### Create 2 features:
1- Machine name: 'ha_common_fields'
  - Human-readable name: HA Common fields

This feature will contain the base field portion of any custom fields that were created for your content types.

2- Machine name: 'ha_public'
  - Human-readable name: HA Public pages

This feature will contain all of the content types, views, menus, and other configuration required to replicate your work from assignment 8. This feature will contain field instances, but **will not** contain *any* field bases for any content type.

*Submit a pull request with each of your feature modules, as well as the modules that were necessary for your content types and views.*

*Each module must be in its own commit.*

Write the instructions for deploying your public pages on someone else's environment.
For example:
1- enable the feature modules ha_public and ha_common_fields
2- Create the following pages using the Basic page content type:
  - Maintenance
  - etc..
3- Create a few location nodes with addresses
4- Visit the service areas page at this URL: __

**Place your instructions for deployment here**