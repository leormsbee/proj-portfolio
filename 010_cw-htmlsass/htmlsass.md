# Installing and compiling SASS
In this assignment, we will work on installing and compiling SASS.  

## Answering Tasks
For this assignment, you will be committing changes to:  
- files/continuousgood/style.scss  
- files/continuousgood/style.css  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
Create a branch based off of **the following TAG**: `drupal-20170308-htmlsass`, using the following convention:
** - [Topic]-[Assignment Number]-[Your initials]**

For example, after running `git fetch --all` , Ashraf Abed would run the following command to create a branch based off the tag: ```git checkout -b sass-cw-10-aa drupal-20170308-htmlsass```.

Upon completing a section, **save the file, git add, and git commit your changes.**

Open the continuousgood folder. It can be found at `da-assignments/files/continuousgood`. It contains several files that will be necessary for working on this assignment, including:
- **style.scss**: this is the SASS file you will use to write and compile your CSS.
- **style.css**: this is the CSS file that will be **automatically generated** (compiled) based on your edits to the style.scss file.

Task 1 - Install SASS
- cd into academyvm and run ```vagrant up```.
- SSH into vagrant: ```vagrant ssh```.
- Install SASS: ```sudo gem install sass```.

*SASS is now installed on your server!*  

Task 2 - Compile your CSS into SASS.
- Open the style.scss file located in the continuous good folder using SublimeText.
- In your command line, run ```sass style.scss style.css``` to compile the SASS into CSS. This means a CSS file named `style.css` will be generated from the SASS file named `style.scss`.
- Open your style.css file and observe the organization of the compiled code!
- Commit the new style.css file.

Task 3 - One benefit of SASS is the ability to use nested selectors to prevent the need to rewrite selectors multiple times. To demonstrate this, use nested syntax to rewrite CSS code targeting the header element.
- Rewrite any styling targeting the ```header``` element using nested syntax.
- In your vagrant environment, `cd` into the continuous good folder (`/var/www/dev-1/da-assignments/files/continuousgood`)
- Run ```sass style.scss style.css``` to compile the SASS into CSS.
- Commit your changes.

Task 4 - Another benefit of SASS is the ability to use variables to allow the storing of any value. To demonstrate this, let us create a variable and use it throughout our SASS file.
- One css value that is commonly used throughout the code is the breakpoint ```max-width: 1130px```. Create a variable called $desktop-breakpoint, give it the value of ```"max-width: 1130px";```, like this: ```$desktop-breakpoint: "max-width: 1130px";```
- In your style.scss file, replace every instance of ```max-width: 1130px;``` with the variable `$desktop-breakpoint`.
- In your vagrant environment's continuousgood folder, run ```sass style.scss style.css``` to compile the SASS into CSS.
- Look at your style.css file to see if the variable worked. You should see ```max-width: 1130px;``` everywhere you used the $desktop-breakpoint variable.
- Commit your changes.

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] sass-cw-10-aa).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the main da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).

