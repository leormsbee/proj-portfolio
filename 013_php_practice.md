# Practice PHP
In this assignment, we will begin using PHP.

## Answering questions
For this assignment, you will be committing changes to:
- 009_phpractice.md (the file you are reading)
- The index.php file in your PHP repository.
  - Accessible via symlinks/php/a9.php
  - You will need to pull the latest updates to the master branch in the php repo to get a9.php

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for question 1:*  
Ashraf Abed would create a branch named: ```php-009-aa```

Complete the following questions in symlinks/php/index.php, using the PHP language.
1- Define a variable called ‘name’, use it to store a string with your first name.

2- Print the text "I am (your name)", using the $name variable from question 1 to print your name.
  - You will need to concatenate (combine) the $name variable with the s "I am ". 

3- Call the function string_to_array, passing your $name variable as an argument.
  - Set a new variable, ```$name_array```, equal to the return value of this function call.

4- Call the function string_to_object, passing your $name variable as an argument.
  - Set a new variable, ```$name_object```, equal to the return value of this function call.

5- Create a function named print_name
  - The function should take 1 argument
    - The argument will either be a string, object, or array
  - ```If``` (use an if statement) the argument supplied to the function is:
    - an array:
      - print the 0th element of the array
    - an object:
      - print the property of the object named ```value```
    - a string:
      - print the string
  - The function does not need to have a return value

6- Call the function you created 3 times:
- Once, send it the argument: $name
- Once, send it the argument: $name_array
- Once, send it the argument: $name_object

7- In your own words, describe the difference between:
- Passing variables by value
- Passing variables by reference
*Write your answer here*

8- Visit php.academyvm.com/a9.php
  - Paste the output of the page here.

## Pull requests
- Submit one pull request to the assignments repo with the changes made to this file
- Submit one pull request to the php repo with the changes made to a9.php
