# Classwork - Using PHP functions and variables.
In this homework assignment, we will practice using PHP functions and variables.

## Answering questions
For this assignment, you will be committing changes to:
- Your da-assignments repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**
** - [Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*
Ashraf Abed would create a branch named: ```cw-php-009-aa```

For PHP to work, you must run vagrant up successfully and place your da-assignments folder inside one of your php environments. For example, I would place my da-assignments folder inside the dev-1 folder. To see your PHP being rendered, you would use your browser to visit the url to your php file. For example, to see the PHP output of my php file located at da-assignments/cw_009_php/index.php, I would use my browser to visit dev-1.academyvm.dev/da-assignments/cw_009_php/index.php.

**After each question, visit your assignment's URL to test your work."

1 - In your cw_009_php/index.php file, create a function named writeMessage which takes no parameters (aka arguments). In the function's body, echo a sentence of your choosing. After creating the function, call the function. Commit your answer to cw_009_php/index.php .


2 - In your cw_009_php/index.php file, create a function named whatIsToday which takes no parameters (arguments). In the function's body, use the php `echo` and `date` functions to print out a sentence that says today's exact date in the following example format: Monday January 2, 2016. The date must be printed using the `date` function. Paste the code you created below this line:


3 - In your cw_009_php/index.php file, create a function named additionFunction. The function should accept 2 parameters by value named `$num1` and `$num2`. In the function's body, create a variable named $total and set it equal to the sum of the two variables you used as parameters (`$num1` and `$num2`). Also inside the function's body, use php's `echo` to display the sum of the two variables. After creating the function, call the function and pass it two parameters in the form of numbers and ensure you see the expected output.


4 - Below, we have two functions. One of the functions is passing its variables by reference while the other is passing it by value.
 - Which function is passing a variable by reference? Write your answer here: 
 - Copy these functions to your cw_009_php/index.php file.
 - One by one, call each function, and pass the $num variable to each function. After calling each function, use `echo` to display the current value of the `$num` variable.

```
         function addFive($num) {
            $num = $num + 5;
         }

         function addSix(&$num) {
            $num = $num + 6;
         }

         $num = 10;
```

## Submitting your assignment
### Step 1
Git add and commit your cw_009_php/index.php file along with the file you are reading right now (if any changes were made to this file). Push the branch to your fork of the da-assignments repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
