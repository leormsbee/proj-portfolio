# Create theme for American Relief Coalition for Syria (ARCS)
In this assignment, we will create a Drupal theme for ARCS.

## Answering questions
For this assignment, you will be committing changes to:
- classwork_001_theme_arcs.md (the file you are reading)
- Your proj-arcs repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** -[Topic]-cw-[Assignment Number]-[Your initials]**  
(cw stands for classwork)  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```arcs-theme-cw-001-aa```  

This work should be completed on your local ARCS website.  

1- Download and install the Zen theme
  - It should reside in sites/all/themes
  - Using drush, you can enable it with the ```drush en``` command, similar to modules
  - Or, as admin, click 'Appearance' and enable using the UI

2- Read the README from the Zen theme
  - Every base theme is different, so you must read the documentation in the Zen theme before starting.
  - The first file to read is README-first.md
  - Zen has very thorough and valuable documentation

3- Open the Drupal.org instructions for creating a subtheme
https://www.drupal.org/node/225125

4- Create a subtheme named: ARCS Theme (arcs_theme)  
  - Use the STARTERKIT provided by Zen  
  - *Commit this subtheme*  

5- Enable your subtheme, then set it as your default theme  

6- Copy the footer and page.tpl.php files to your subtheme
  - You will need to clear cache for these to work
  - Ensure you place them in the right folder. There is only 1 location they will work from  
  - *Commit these files*

7- Time permitting, begin styling the ARCS theme in class.
