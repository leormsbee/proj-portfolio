# Generate a new SSH key
In this assignment, we will generate an SSH key to be used for authentication over SSH.

## Answering questions
For this assignment, you will be committing changes to:
- Your da-assignments repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch based off of the master branch using the following convention:**  
** -[Topic]-[Assignment Number]-[Your initials]**

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```hw-ssh-027-aa```  

This work should be completed in your da-assignments folder. The instructions are different for Windows and Mac users.

## Mac users only (windows instructions follow)
### Mac users Task 1: Generate a new SSH key

- Open the Terminal.

- Run the following command, but replace `[YOUR-EMAIL@site.com]` with your github.com e-mail address.
`ssh-keygen -t rsa -b 4096 -C "[YOUR-EMAIL@site.com]"`
You have just generated a new SSH key.

When you're prompted to "Enter a file in which to save the key," **press Enter**. This accepts the default file location.

It will ask you for a passphrase. You can either fill in a new password then press enter, or do not enter a password and press enter.

### Mac users Task 2: Adding your SSH key to the ssh-agent
Run the following in the terminal: `eval "$(ssh-agent -s)"`

If you're using macOS Sierra 10.12.2 or later, run these commands:
- `nano +99999 ~/.ssh/config`
Press `enter` then paste this:
```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```
Save the file by pressing: `ctrl` + `x`. Then type `y` and then press `enter`.

Run: `ssh-add -K ~/.ssh/id_rsa`

## Windows users only (mac instructions above)
### Windows Task 1 - Create new SSH Key
- Open Git Bash
- Run the following command, but replace `[YOUR-EMAIL@site.com]` with your github.com e-mail address.
`ssh-keygen -t rsa -b 4096 -C "[YOUR-EMAIL@site.com]"`
You have just generated a new SSH key.

When you're prompted to "Enter a file in which to save the key," **press Enter**. This accepts the default file location.

It will ask you for a passphrase. You can either fill in a new password then press enter, or do not enter a password and press enter.

### Windows users Task 2: Adding your SSH key to the ssh-agent
Run the following in Git Bash: `eval "$(ssh-agent -s)"`

Now run: `ssh-add ~/.ssh/id_rsa`

## Submitting your assignment

### Windows and Mac users
Copy *only* the **public** (ends in .pub) key into this assignment's folder with this command:
- `cp .ssh/id_rsa.pub ~/Desktop/debugacademy/sites/dev-1/da-assignments/027_hw-sshkeys/`

### Step 1
Push the branch you created for this assignment to your fork of the da-assignments repository (e.g. git push [remote-name] [branch name]).

### Step 2
Create a pull request to the da-assignments repositiory on github. Once you visit the da-assignments repository on github (https://github.com/debugacademy/da-assignments), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
