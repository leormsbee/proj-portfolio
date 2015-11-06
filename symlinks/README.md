# What is this?
This folder contains symlinks to repositories we will be regularly accessing in class.  

Symlinks work like shortcuts to other files or folders.  

We will create symlinks in this folder which point to our repositories. This way, everyone in the class can access all of their repositories from one centralized location; this folder.

## How to create a symlink
Step 1: `cd` to where you want the symlink, or shortcut, to be placed  
Step 2: Determine the path to the file from where you are to the file/folder you want a shortcut to  
  - Example: `../001_git.md` is the relative path to my first homework assignment  
  - Example: `~/Sites/haacademyvm` is the path to my HA repo  
Step 3: Create the symlink using the following command:  
- ```ln -s [path of file/folder] [alias]```  
  - `[path of file/folder]`: This is the path you must type`The path to your repo on your computer`  
  - `[alias]`: `what the symlink, or shortcut, will be named`  

## Which symlinks to create
- `[alias]`: vagrant  
- `[path of file/folder]`: Path to your vagrant box repo  
  - This is the folder you ran `vagrant up` in  

- `[alias]`: halighting  
- `[path of file/folder]`: Path to your HA Lighting Drupal repo  

- `[alias]`: contgood  
- `[path of file/folder]`: Path to your Continuous Good Drupal repo  

- `[alias]`: php  
- `[path of file/folder]`: Path to your PHP repo  

- `[alias]`: lessons  
- `[path of file/folder]`: Path to your da-lessons repo  
