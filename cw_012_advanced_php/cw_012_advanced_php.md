# Advanced PHP
In this assignment, we will use more advanced PHP as well as more Drupal-specific functions.

## Answering questions
For this assignment, you will be committing changes to:
- Your proj-themes repository
- Your da-assignments repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Tasks
**Create a branch based off of the develop branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```cw-themes-012-aa```  

This work should be completed on your local proj-themes website. 

**Important: You must base your work off of the latest develop branch, which comes with Classwork 11, before beginning this assignment.**

1 - Download and enable the `devel` module. This module provides pages and PHP functions which are very useful for development. Typically, this module is only enabled on development websites.

2 - **Create a new theme node** on your website. **Set the Price field equal to 1**. After creating it, visit the theme page directly. Record the node ID, the unique identifier for your node. This is displayed in the URL. For example, if it says `node/1`, then `1` is the node ID.

3 - Edit our custom module's .module file, `athemes/athemes.module`. Create a function which implements (uses) the ```hook_page_alter``` hook. You do this by creating a function with the same name as the hook, but replace the word `hook` with the name of your module. As described in this hook's page of the Drupal API, pass it the ```$page``` variable by reference. In-between the function's curly braces, display the $page variable using the `dpm` function, like so: `dpm($page, 'page');`

4 - Clear Drupal's cache `drush cc all` , then visit any page while logged in as administrator to see the page variable.

5 - Now we'll call Drupal's ```node_load($nid)``` function to load the node object. All of this code will be placed in the hook_page_alter function from question 3. First, set `$nid` equal to the node ID from question 2. Then, run the code: ```$node = node_load($nid);``` to load the node object and store it in a variable named `$node`. 

6 - To view the contents of your node, we will again use ```dpm()```, which can print nodes, objects, arrays, and more. At the bottom of the hook_page_alter function from question 3, call the `dpm()` function, and pass it the ```$node``` variable as the first argument, and the string `'node'` as the second argument, separated by commas.

7 - Clear Drupal's cache `drush cc all` , then visit any page while logged in as administrator to see both the page variable and the node variable. The node object/array contains the fields and properties for the node you loaded.

8 - Now that we have loaded our node, let's modify it programmatically. Look at the node object displayed on your website to see where the `field_price_` value is stored. It is at `$node->field_price_['und'][0]['value']`. Remember, `->property_name` is used to access properties from an object, while `['key_name']` is used to access array elements. We will change the value in question 9.

9 - Run this code which will increment the value by 1: `$node->field_price_['und'][0]['value']++;` . For this value to be saved, we need to save our node. Drupal has a function for this: `node_save($node);` , where $node is the object we modified.

10 - Visit your node's page. Re-load the page repeatedly, and watch the value of the node increase with each page refresh! Commit your work at this point.

11 - We will now get some practice using foreach loops. In PHP, a "foreach loop" executes a block of code a specified number of times. 

The syntax of foreach loops is as follows:

```
foreach ($my_array as $value) {
    // code to be executed;
} 
```
It is also possible to loop through objects rather than arrays, although it is done less commonly.

For every loop instance, the value of the current array element is assigned to the variable ```$value```, until the last element of the array is traversed.

Begin by creating a variable named ```$my_array```. Set this variable equal to an array with 4 elements, `'one', 'two', 'three', 'four'`. Place this variable within your existing `hook_page_alter` function. After that, lets loop through each one of these items.

Create a foreach loop using the above syntax where you use `dpm($value);` within the body of the foreach loop to display each value in the array. Clear your cache, refresh your drupal page, and look for your array elements! Commit your work at this point.

12 - You can use `grep` to search within the output of another command. In your proj-themes directory, run ```git log | grep word_to_search```. Replace word_to_search with the word `sass`. This will first run git log, but will then immediately search through the output of the git log command for the word sass; together, this shows us any commit messages where the word "sass" is found. Paste the output below this line:

13 - Use the ```grep``` (global regular expression print) command to search the entire da-assignments folder for the word "String".
- Type ```grep -r 'String' [location of folder]```. It is case sensitive. You will replace ```[location of folder]``` with the actual path the folder you are trying to search through is located. For example, I used the following command: ```grep -r 'String' ~/Desktop/debugacademy/sites/dev-1/da-assignments```. Adding -r makes the search recursive, which means grep will also search all of the subfolders in the folder you specified.

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).
Push the branch to your fork of the da-assignments repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create pull requests for the branches.
