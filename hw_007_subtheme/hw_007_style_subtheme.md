# Begin styling the subtheme for the Academy Themes website
In this assignment, we will style the header and footer for the Academy Themes subtheme using SASS.

## Answering questions
For this assignment, you will be committing changes to:
- hw_007_style_subtheme.md (the file you are reading)
- Your proj-themes repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## SASS set up
Because SASS is a preprocessed language, you must set your environment up to actually preprocess your SASS into CSS.  

This only needs to be done once on your server. If you run 'vagrant destroy', then 'vagrant up', you would need to follow the initial installation instructions again as well.  

### Initial SASS installation
- Install ruby
  - Edit academyvm/config.yml
  - Uncomment (delete the ```#```) the line with: ```- ruby```
- Run ```vagrant reload```
- Run ```vagrant provision```
- SSH into vagrant: ```vagrant ssh```
- Install SASS: ```sudo gem install sass```
- ```cd``` into your subtheme
- Per Subtheme's SASS/README.txt, run: ```bundle install```

*SASS is now installed on your server.*

### Compiling SASS
For your changes to .scss files to be read by your browser, they must be compiled into CSS. Every time you make any change to any SASS file, you must compile the SASS to CSS. The compiled CSS will be placed in the file css/style.css.  

To compile your theme's SASS (at any time):  
- Run ```bundle exec compass watch``` in your (sub)theme's root directory
  - This will OVERWRITE the file css/style.css with the compiled SASS files
  - css/style.css will automatically be overwritten with the output of all of the theme's .scss files
- Leave this command running as long as you are editing your subtheme's ```.scss``` files
  - Open a new terminal window if you need to use the terminal while this command is running

## Questions
**Create a branch _based off of the branch you used for the cw_008_create_subtheme.md assignment, NOT the master branch, using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```hw-themes-008-aa```  

This work should be completed on your local proj-themes website.  

1- Style the theme's header to match the Academy Theme design's header as much as possible.
  - All widths, heights, background colors should be the same
  - Font faces and font sizes do not need to be exactly the same as the design
  - Use your previous homework assignment as a guide for how to accomplish the design goals using CSS

*tips*:
- 'Content' on the website (menu links, footer links), should not be written ('hardcoded') in the tpl files.
  - Instead, don't worry about what the words say. Be concerned with the styling of each menu link.
- You can watch how Ashraf Abed approached this assignment for debugacademy.com at this video:
  - https://www.youtube.com/watch?v=ahn5qnUqEmQ
  - Note: one difference is the theme in the video did not use SASS
    - Meaning although Ashraf edited ```css/components/misc.css```, you would instead edit ```sass/components/_misc.scss```
     - Also, Ashraf did not have to compile the SASS into CSS. You will need to follow the 'Compiling SASS' steps above after making any changes.  
- Pick small pieces of the header to implement into your theme. When one part looks right, commit it. Don't wait until the whole header is ready to commit your work.
  - For example, Replace the default zen logo with the Academy Theme's logo, then commit that change.
  - Then, adjust the styling for the main menu links. When individual links' styling is correct, commit that change.
  - Then, place the logo the proper amount of pixels from the top and the left. When this is correct, commit that change.

2- Style the theme's footer to match the Academy Theme design's footer as much as possible.
  - All widths, heights, background colors should be the same
  - Font faces and font sizes do not need to be exactly the same as the design
  - Use your previous homework assignment as a guide for how to accomplish the design goals using CSS
