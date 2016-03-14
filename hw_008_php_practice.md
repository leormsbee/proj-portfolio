# Practice PHP  
In this assignment, we will begin using PHP.  

## Answering questions  
For this assignment, you will be committing changes to:  
- hw_008_php_practice.md (the file you are reading)  
- The ha_008.php file in our public_html repository.  
  - Details for accessing the repository are listed later in the assignment  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing  
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions  
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for question 1:*  
Ashraf Abed would create a branch named: ```php-008-aa```  

0- Clone the public_html repository into your sites/php/ folder:  
  - First, ```cd``` into the existing folder: sites/php/  
  - Then git clone the repository: ```git clone https://github.com/debugacademy/public_html.git ./```  

Complete the following tasks within the file sites/php/ha_008.php, using the PHP language. *To test any PHP changes you make, you must visit the file at the URL: http://php.academyvm.dev/hw_008.php *  
1- Create a variable called ‘my_name’ by setting it equal to a string with your first name.  

2- Print the text "I am (your name)", using the $my_name variable from question 1 to print your name.  
  - You will need to concatenate (combine) the $my_name variable with the string "I am ".  
  - Use the PHP function 'print' to print the string.  

3- Call the function string_to_array, passing your $my_name variable as an argument.  
  - Set a new variable, ```$name_array```, equal to the return value of this function call.  

4- Call the function string_to_object, passing your $my_name variable as an argument.  
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
- Once, send it the argument: $my_name  
- Once, send it the argument: $name_array  
- Once, send it the argument: $name_object  

7- In your own words, describe the difference between:  
- Passing variables by value  
- Passing variables by reference  
*Write your answer here*  

8- Visit php.academyvm.com/hw_008.php   
  - Paste the output of the page here.  

## Pull requests  
- Submit one pull request to the assignments repo with the changes made to this file  
- Submit one pull request to the public_html repo with the changes made to hw_008.php.php  
  - You will need to 'Fork' the public_html repository, add your fork as a remote alias, and push your branch to the fork to complete this step.
