# Assignment 1: Intro to the Command Line
In this assignment we will learn to use common commands on the command line. You will be using many of these commands daily as a developer.

## To BEGIN this homework assignment:
Save this file to your computer by right-clicking (and choosing 'save as') for this link here:  
https://github.com/debugacademy/da-assignments/raw/master/hw_001_command_line/hw_001_command_line.md  
You will answer questions by editing the downloaded homework assignment file directly. I recommend moving the file to your debugacademy folder on your machine's Desktop.  

## To submit this homework assignment, simply email  ( tasks@debugacademy.com ) this file with the answers filled in. After each task, there will be space to paste your answer.
**You can use lessons provided by the class as well as google to answer the questions.**

Terminology tips:  
- 'Folders' are referred to as 'directories'.  
- 'Terminal', 'Bash', and 'Command line' are used interchangeably.  

## Tasks

1 . Open the Terminal (Mac Users) or Git Bash (Windows Users). 
- Navigate to the debugacademy folder on your desktop using the ```cd``` (change directory) command.
    - For Mac or Linux users, this can be done by typing ```cd ~/Desktop/debugacademy```. As mentioned in Lesson 1, the shortcut ```~/``` is equivalent to writing ```/Users/[your account]```.
    - For windows users, you will need to use the ```pwd``` (print working directory) command to figure out the absolute path to your debugacademy directory. Yours should look something like this ```c:\Users\(username)\Desktop\debugacademy```. You should see your username or computer's user name as part of the path.
- Paste the last few lines from your command line window directly below this question. Answer:

For example, my last few lines would look like this: 
- `Alis-MBP:~ Ali$ cd /Users/Ali/Desktop/debugacademy/`
- `Alis-MBP:debugacademy Ali$`

2 . Inside your debugacademy directory, create a new directory called assignment_1 using the ```mkdir``` (known as the "make directory" or "create directory") command. Type ```mkdir assignment_1``` when you are in your "debugacademy" directory. To verify it was created successfully, open your debugacademy directory (folder) outside of the command line (as you normally would). You should see a new directory named assignment_1 inside of it.
- Paste the last few lines from your command line window directly below this question. Answer:

For example, my last few lines would look like this:
- `Alis-MBP:debugacademy Ali$ mkdir assignment_1`
- `Alis-MBP:debugacademy Ali$`

3 . On your Desktop, create a directory named documents. This should also be done using the mkdir command. After that, let us use the ```mv``` (known as the move file or directory command) to move our newly created documents directory inside the assignment_1 directory we created.
- To do this, cd to the Desktop and type ```mv documents/ debugacademy/assignment_1/```. This will move the 'documents' directory inside the 'assignment_1' directory.
- Pro-tip: To navigate from your debugacademy folder back up to your desktop, use `cd ../`, because the Desktop folder is only one directory above the debugacademy folder. Two dots denotes 'one level up', as explained in lesson 1.
**Paste the last 4 lines from your command line below.** Answer:

For example, this is what the last 4 lines of my command line look like:
- `Alis-MBP:debugacademy Ali$ cd ../`
- `Alis-MBP:Desktop Ali$ mkdir documents`
- `Alis-MBP:Desktop Ali$ mv documents/ debugacademy/assignment_1/`
- `Alis-MBP:Desktop Ali$`

4 . After using ```cd``` to enter your Desktop directory, use the ```pwd``` command to see the absolute path to your desktop. For example, my absolute path is ```/Users/Ali/Desktop/```. You should see your username or computer's user name as part of the path. In this case, my username is Ali.
**Paste the absolute path to your Desktop below.** Answer:

5 . Navigate to the debugacademy directory using the ```cd``` command through the absolute path.
- Use your answer from Question # 4 as the argument to the cd command. For example, I used the following command to navigate to the debugacademy directory: ```cd /Users/Ali/Desktop/debugacademy```. **Paste the last few lines from your command line below.** Answer:

6 . Navigate to the assignment_1 directory from the debugacademy directory which you navigated to in question # 5 using the relative path. The relative path is simply ```assignment_1/```.

Pro-tip: as you are typing the first few letters of the name of an existing directory, tap the "tab" button once. You will notice that the terminal or command prompt will automatically fill in the remainder of the partially typed directory name, if there is a single match. For example, if you are in the Desktop then type ```cd debu``` followed immediately by the "tab" button, the terminal/prompt will automatically turn debu into debugacademy.

7 . - Let us use the ```ls``` (list) command to get a list of the files and directories inside our assignment_1 directory. To do this, simply run the command ```ls``` from within your assignment_1 directory. Your assignment_1 directory should only have one other directory inside of it.
**Paste the last few lines from your command line/prompt below.** Answer:

For example, this is what the last 4 lines of my command line look like:
- `Alis-MBP:debugacademy Ali$ cd assignment_1/`
- `Alis-MBP:assignment_1 Ali$ ls`
- `documents`
- `Alis-MBP:assignment_1 Ali$` 

7 . As mentioned in lesson one, you can add flags to the ```ls``` command. These command line flags allow you to specify more options. Let us get some practice using the ```-la``` flag, which will output a long listing format of all the files and directories inside our current directory.
-Make sure that you are in the assignment_1 directory. Inside the command line, type ```ls -lah```.
**Paste the last 6 lines from your command line/prompt below.** Answer:

8 . ```cd``` into your documents directory and using the ```mkdir``` command, create another directory named temporary.
- Use the  ```ls -lah``` command to verify that the new directory exists.
- Let us now delete this directory using the ```rm -r``` command. ```rm -r``` deletes a directory and all of its sub directories. The ```-r``` flag stands for 'recursive'. If we were simply deleting a file, we wouldn't need to use the ```-r``` flag.
- **Always use the rm -r command with care. It does NOT move deleted files and folders to the trash, it permanently deletes them.**
- Use the ```ls -la``` command once again to verify that the directory has been deleted.
**Paste the output from the last few commands below.** Answer:

For example, this is what the last 13 lines of my command line look like:
- `Alis-MBP:assignment_1 Ali$ cd documents/`
- `Alis-MBP:documents Ali$ mkdir temporary`
- `Alis-MBP:documents Ali$ ls -la`
- `total 0`
- `drwxr-xr-x  3 Ali  staff  102 Oct 27 15:12 .`
- `drwxr-xr-x  3 Ali  staff  102 Oct 27 14:44 ..`
- `drwxr-xr-x  2 Ali  staff   68 Oct 27 15:12 temporary`
- `Alis-MBP:documents Ali$ rm -r temporary/`
- `Alis-MBP:documents Ali$ ls -la`
- `total 0`
- `drwxr-xr-x  2 Ali  staff   68 Oct 27 15:13 .`
- `drwxr-xr-x  3 Ali  staff  102 Oct 27 14:44 ..`
- `Alis-MBP:documents Ali$`

9 . Use the ```grep``` (global regular expression print) command to search the current file you are editing for the word "example".
- Type ```grep 'example' [location of file]```. You will replace ```[location of the file]``` with the actual path where this first_assignment.md file exists. For example, I used the following command: ```grep 'example' ~/Desktop/debugacademy/first_assignment.md```.
- **Paste the output of the command line/prompt below.** Answer:

10 . Save this file (first_assignment.md), then copy it to the assignment_1 directory we created using the ```cp``` (copy) command. You can use either the absolute or relative path.
- ```cd``` into the assignment_1 directory and use ```ls``` to verify the copy is there.
- **Paste the output of the last few commands and save this file.** Answer:

11 . Use the `diff` command to print the difference between this file and the copy that you made. 
- **Paste the output of the command line and save this file.** Answer: 

## To submit this homework assignment, simply email  ( tasks@debugacademy.com ) this file with the answers filled in. 
