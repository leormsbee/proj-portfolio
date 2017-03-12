# Compiling SASS
In this assignment, we will merge/combine our HTML/CSS work from previous assignments and get more practice compiling SASS.  

## Answering Tasks
For this assignment, you will be committing changes to:  
- files/continuousgood/style.scss  
- files/continuousgood/style.css
- files/continuousgood/homepage.html  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
**Create a branch based off of the master branch, using the following convention:**
** - [Topic]-[Assignment Number]-[Your initials]**  

For example, Ashraf Abed would run the following command to create a branch based off the master branch: ```git checkout -b sass-hw-11-aa master```.  

Open the continuousgood folder. It can be found at `da-assignments/files/continuousgood`. It contains several files that will be necessary for working on this assignment:
- **style.scss**: this is the SASS file you will use to write and compile your CSS.
- **style.css**: this is the CSS file that will be compiled based on your edits to the style.scss file.

Task 1 - Merge your work from assignments 6 and 8 so that all your code from the two assignments is combined.
- Run ```git branch``` to see what branches you have created so far.
- Merge the branch from Assignment 6, Task 3.
	- Run ```git merge [branch you used for assignment 6 task 3]```
	- Fix merge conflicts if necessary.
	- Save the files
	- Run ```git status``` to see which files were modified.
	- Run ```git add [file name or names]``` to add the files.
	- Commit your changes

- Merge the branch from Assignment 8, Task 1.
	- Run ```git merge [branch you used for assignment 8 task 1]```
	- Fix merge conflicts if necessary.
	- Save the files
	- Run ```git status``` to see which files were modified.
	- Run ```git add [file name or names]``` to add the files.
	- Commit your changes

- Merge the branch from Assignment 8, Task 2.
	- Run ```git merge [branch you used for assignment 8 task 2]```
	- Fix merge conflicts if necessary.
	- Save the files
	- Run ```git status``` to see which files were modified.
	- Run ```git add [file name or names]``` to add the files.
	- Commit your changes

Task 2 - Prepare style.scss file
- rename the file **files/continuousgood/style.css** to **files/continuousgood/style.scss**. This can be done by pasting this entire command:
  - `cd ~/Desktop/debugacademy/sites/dev-1/da-assignments/files/continuousgood && mv style.css style.scss`
- Now your style.css file should be gone, and style.scss will contain all of your CSS. The **style.scss** file is the sass file we will be using from now on.
	- Run ```git status``` to see which files were modified.
	- Run ```git add [file name or names]``` to add the files.
	- Commit your changes
- Once you have ensured that all your code from the style.css file were copied into the style.scss file, **delete all the contents of the style.css file**. Ensure that it is empty by visiting your homepage.html file using the browser. You should see no styling.

Task 3 - Compile the sass
- cd into academyvm, run `vagrant up`
- cd into academyvm, run `vagrant ssh`
- cd to where your style.scss file is located: `cd /var/www/dev-1/da-assignments/files/continuousgood`
- Compile the sass by running ```sass style.scss style.css```. This command says to compile the **style.scss** sass file into CSS and place it in the **style.css** file.
- Visit your homepage.html file once again using the browser and you should see the styling again. Open the **style.css** file and observe the organization of the compiled code!
- From this point forward, always write all of your css inside the **style.scss** file. When you'd like to see your changes, save the file and compile your sass into CSS again to see your changes.
- Run ```git status``` to see which files were modified.
	- Run ```git add [file name or names]``` to add the files.
	- Commit your changes

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] sass-hw-11-[your initials]).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the main da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
