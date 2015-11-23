# Theme HA Lighting
In this assignment, we will create a Drupal theme for HA Lighting.

## Answering questions
For this assignment, you will be committing changes to:
- 011_theme_ha.md (the file you are reading)
- Your proj-ha repository (symlinks/halighting)

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```ha-theme-011-aa```

This work should be completed on your HA Lighting website.

1- Download and install the Zen theme
  - It should reside in sites/all/themes
  - Using drush, you can enable it with the ```drush en``` command, similar to modules
  - Or, as admin, click 'Appearance' and enable using the UI

2- Read the README from the Zen theme
  - Every base theme is different, so you must read the documentation in the Zen theme before starting.
  - The first file to read is README-first.md
  - Zen has very thorough and valuable documentation

*Question*: Define each of the following, based on your reading in the Zen theme:
- A base theme: *Place your answer here*
- A sub theme: *Place your answer here*
- A starter theme: *Place your answer here*

3- Read the Drupal.org instructions for creating a subtheme
https://www.drupal.org/node/225125

*Question:* Describe how style sheet inheritance works from base theme to subtheme. Include default inheritance, and how to override a parent theme's stylesheets.

4- Create a subtheme named: HA Lighting (ha_lighting)
  - Use the STARTERKIT provided by Zen
  - *Commit this subtheme*

5- Enable your subtheme

6- Copy the header, footer, and page .tpl.php files to your subtheme
  - You will need to clear cache for these to work
  - Ensure you place them in the right folder. There is only 1 folder they will work
  - *Commit these files*

7- *Question:* What .tpl.php file would you need to create to override the default block styling?
Write your answer here.

8- *Question:* What .tpl.php file would you need to create to override the default block styling on *only* the homepage?
Write your answer here.
