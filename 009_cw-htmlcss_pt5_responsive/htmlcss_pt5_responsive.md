# Responsive Design
In this assignment, we will work on making the Continuous Good design responsive.  

## Answering Tasks
For this assignment, you will be committing changes to:  
- files/continuousgood/homepage.html  
- files/continuousgood/style.css  
- The file you are reading

**Please use SublimeText to edit the HTML and CSS files.**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
Before starting any assignment, you should checkout the master branch and then update it by running ```git pull [remote] master```. The remote's name should be the remote that points to https://github.com/debugacademy/da-assignments.git. For this assignment, we will be creating a branch based off of master and then merging in a tag.
- Run ```git fetch --tags``` to download all the tags
- Create a branch based off of master branch, using the following convention:
** - [Topic]-[Assignment Number]-[Your initials]**  

For example, Ashraf Abed would run the following command to create the branch: ```git checkout -b responsive-cw-9-aa master```.  
- Merge in **the following TAG**: `drupal-20170305-htmlcsspt5`. You would do this by running ```git merge drupal-20170305-htmlcsspt5```.
- To exit the merge commit screen, click on ```ESC``` and then type ```:wq``` then click on Enter.

Upon completing a section, **save the file, git add, and git commit your changes.**

Protip: After editing this file, you can run git status to see what files were changed and git diff [file_name] to see what exactly was changed in the file.

Open the continuousgood folder. It can be found at `da-assignments/files/continuousgood`. It contains several files that will be necessary for working on this assignment:
- **homepage.html**: this is the HTML file you will be modifying and adding HTML code to. We have outlined where your code should be written for each section within the file by using HTML comments. You will replace the comment (the `<!-- [text] -->`) with your HTML for that section.
- **style.css**: this is the CSS file you will be modifying and adding CSS code to.
- **continuousgood.jpg**: this is the image of the continuous good homepage design that we are coding.
- **images**: this is a folder with images you will need as you write the html and CSS for the homepage design.

Task 1 - Determine breakpoints
- Open the homepage.html file using Google Chrome. Ensure the window is as wide as possible, taking up about 100% of your screen size.
- Activate the inspector tool by right clicking the webpage and pressing 'Inspect Element'.
- Slowly shrink the width of the browser window. When minimizing the window and while the inspector is open, you will see a measurement in the top right corner of the browser window in the format of width x pixels (i.e. 1340px x 500px). This measurement is provided by the inspector tool and tells us the width and height of the current page we're on. 
- At what width does the design begin to "break", or lose its intended structure? This number is our first breakpoint.
*Write your answer here:*

**Upon completion of Task 1, save the assignment file you are reading, git add, and git commit your work.**  

Task 2 - Make the "One Action, Continuous Good" section responsive. This means that no matter how small you minimize the width of the browser, you should never have to scroll right or left to see the site's content.
- This can be done by adding CSS media queries

**Upon completion of Task 2, save your changes to the CSS and HTML files, git add, and git commit your work.**

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] responsive-cw-9-aa master).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the main da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
