# Create a preprocess hook to pass a variable to our custom theme.
In this assignment, we will create a variable containing the copyright statement at the bottom of the design.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

This work should be completed on your local proj-me website.

## Tasks
**Create a branch based off the develop branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-theming-031-aa``` 

### Task 1 - Create a variable and assign it the current year
- In your custom theme's proj_me_theme.theme file, create a function called hook_preprocess and pass $variables to it by reference. You should replace the hook with the name of your custom theme.
- Inside this function, we will create a variable called year and give it the value of the date function with only the year ("Y") parameter. For example, I would add the following code:
```
function hook_preprocess(&$variables) {
  $variables['year'] = Replace this text with the date function and pass it the value of the year;
}
```

### Task 2 - Create another variable and assign it the value of your site's name.
- In your custom theme's proj_me_theme.theme file, add another variable to the existing preprocess function.
- Call this variable site_name and assign it the value of the following: ```\Drupal::config('system.site')->get('name')```. This variable will contain your site's unique name, which you set under Configuration > System > Basic site settings

### Task 3 - Pass your variable to the page--front.html.twig file
- Let us use our new $year variable to print the value we set it to on our Drupal site.
- Open your page--front.html.twig file and right above the ```</footer>``` tag, add the following to print your year variable: ```{{year}}```.
- You will also need to add the following to print your site name's variable: ```{{site_name}}```.
- Clear your cache and refresh your drupal site and you should see the contents of your variables in the footer region! You will need to add HTML so that the block says ```© 2017 YOURNAME ALL RIGHTS RESERVED```.
- Style this block to match the design by surrounding the ```{{year}} and {{site_name}}``` variable with HTML and then applying the appropriate sass.

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]). The branch for this assignment was created in Task 2.

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
