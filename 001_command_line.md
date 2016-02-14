# Intro to the Command line
In this assignment, we will learn to use the command line.

## Answering questions
In this assignment, simply edit the homework file itself to answer the questions on it. Your answers will be submitted by e-mailing this file.

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be in your own words**

## Questions
- Open your command line program.  
**Mac users:** This it the 'Terminal' program
**Windows users:** This is the 'Git bash' program (must be downloaded)

- Use the ```cd``` command to navigate to your computer's Desktop. For example, this would be ```cd ~/Desktop``` on a mac. Once you have done so, type ```pwd``` and submit it to confirm you have successfully navigated to your desktop folder.  
Copy and paste the commands written for this problem and their output: [right here]  

- (Done during class) Create a directory named 'debugacademy' using the ```mkdir``` command. To use the ```mkdir``` command, simply type ```mkdir```, a space, and the name of the folder you would like to create.  

- Use the ```cd``` command to enter the new folder named 'debugacademy'. You should simply be able to use ```cd debugacademy```, if you are in your Desktop already.

**If you have not yet installed Xcode(Mac only), Virtualbox, Vagrant, and Git Bash(Windows only), you must do so before proceeding.**

- (Done during class) Clone the drupal-vm (academyvm) repository into your current folder, naming the cloned folder 'academyvm': ```git clone https://github.com/debugacademy/drupal-vm.git academyvm```
  - (Done during class) Upon submitting that command, github will ask for your username and password. When typing your password on the command line, it will not display, even though your password is being typed.

- Clone the da-assignments repository into your debugacademy folder: ```git clone https://github.com/debugacademy/da-assignments.git```

- Clone the course-drupal repository into your debugacademy folder: ```git clone https://github.com/debugacademy/course-drupal.git```

- ```cd``` into the academyvm folder.

- ```cd``` to the folder: ```debugacademy/sites/dev-1```. Tip: Use the ```pwd``` command to see where you are, then see the first lesson (001) for how to ```cd``` 'up' one level, AKA out of the current directory.

- Clone the proj-challies repository into your dev-1 folder: ```git clone https://github.com/debugacademy/proj-challies.git ./```
  - You will need to log in using your github username and password
  - Notice we added an argument of ```./```, which stands for 'current directory'. 
  - This prevents the repository from being placed in a sub-directory.

Perform the following steps only after successfully running ```vagrant up```.

- Download the Database export by visiting this link, then right clicking the 'Raw' button and pressing save as: https://github.com/debugacademy/proj-challies/blob/db/challies-2016Feb13T21-04-41.mysql.gz
  - Save the file into the folder: debugacademy/sites/dev-1

- ```cd``` back into your academyvm folder, and run ```vagrant ssh```

- After running ```vagrant ssh```, ```cd``` into /var/www/dev-1

- Copy and paste your most recent commands and the output here.

- If you use any tutorials on command line, please post their links here.
