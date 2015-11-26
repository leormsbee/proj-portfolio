# Theme HA Lighting - Header, footer, CSS  
In this assignment, we will implement the header, footer, and general CSS styling for our HA Lighting theme which was created in the previous assignment.  

*Although you have team mates, it is likely faster for you to each build your theme separately.* Collaborate on your approach (such as: what .tpl.php files are we editing and why), but you do not need to submit the exact same themes.  

## Answering questions  
For this assignment, you will be committing changes to:  
- 012_theme_ha_part2.md (the file you are reading)  
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

1- Prepare your work station  
For your HTML & CSS start point:  
- Open da-assignments/files/halighting/   
  - Contains homepage.html, with the design's HTML  
  - Contains style.css, with the design's CSS  

Open the zen theme:  
- symlinks/halighting/sites/all/themes/zen  

Open your (sub)theme:  
- symlinks/halighting/sites/all/themes/ha_lighting  

2- HTML for a theme goes in .tpl.php files. To edit the HTML for our theme, we must first look at the parent theme to see which .tpl.php files contain the code for the header, the footer, and the main content areas.  

Review the files in:  
  - sites/all/themes/zen/templates/  

Which .tpl.php file contains the HTML for the header? hint: it likely has a ```<header>``` tag in it. *Write answer here*  

Which .tpl.php file contains the HTML for the footer? hint: it likely has a ```<footer>``` tag in it. *Write answer here*  

3- Copy the 2 .tpl.php files you will be editing for the header and footer (from question 2) from the zen theme to your subtheme  
Copy from:  
  - sites/all/themes/zen/templates/XXX.tpl.php  

Into:  
  - sites/all/themes/ha_lighting/templates/XXX.tpl.php  

4- Using the HTML from da-assignments/files/halighting/homepage.html as a reference, update the appropriate .tpl.php file to create your header.  

5- Write the HTML for the footer in the appropriate .tpl.php file  

6- Reviewing the original, unedited, .tpl.php files from the zen theme, ensure you have not left out any PHP code. PHP code starts with ```<?php``` and ends with ```?>```. If you find that you have removed PHP code that was in the .tpl.php file, decide where it most likely belongs, put it there in its entirety.   

For example, the main menu is displayed with this code, by default:  
```  
    <div id="navigation">  

      <?php if ($main_menu): ?>  
        <nav id="main-menu" role="navigation" tabindex="-1">  
          <?php  
          // This code snippet is hard to modify. We recommend turning off the  
          // "Main menu" on your sub-theme's settings form, deleting this PHP  
          // code block, and, instead, using the "Menu block" module.  
          // @see https://drupal.org/project/menu_block  
          print theme('links__system_main_menu', array(  
            'links' => $main_menu,  
            'attributes' => array(  
              'class' => array('links', 'inline', 'clearfix'),  
            ),  
            'heading' => array(  
              'text' => t('Main menu'),  
              'level' => 'h2',  
              'class' => array('element-invisible'),  
            ),  
          )); ?>  
        </nav>  
      <?php endif; ?>  

      <?php print render($page['navigation']); ?>  

    </div>  
```  

Although you can edit HTML like ```<div id="navigation">```, the PHP is used to dynamically render data from your website. The above example dynamically builds your main menu; that's a feature you want your theme to maintain. You can carefully move the PHP code to the appropriate part of your .tpl.php file, but you should probabaly not be editing the PHP code. Becuase this builds your main menu, you likely would replace your menu's HTML with that PHP code, and let Drupal write the menu's HTML for you.  

6- Write the appropriate CSS for your theme's header at the bottom of:  
sites/all/themes/ha_lighting/components/misc.css  

Generalize CSS only when appropriate. For example, if a font color is right for the whole website, you can set it for the whole website. If it is only appropriate for a specific section, then only set it for that section.  

7- Write the appropriate CSS for your theme's footer at the bottom of:  
sites/all/themes/ha_lighting/components/misc.css  

8- Write the appropriate CSS for general styling (default font color, size, etc), to ensure consistency across the website  

9- Ensure the header, footer, and general CSS rules (font size, color, background color) looks consistent across the website  
