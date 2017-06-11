# Classwork - Initial Environment Setup.
In this assignment, we will set up our development environment.
**Note: You cannot do this assignment without downloading the required software sent in the email prior to the first day of class.**

1 - Using terminal/gitbash, create a folder named `debugacademy` on your machine's desktop. This can be done by navigating to your desktop, then using the mkdir command:
- `cd ~/Desktop`
- `mkdir debugacademy`
- `cd debugacademy`

2 - Using terminal/gitbash, cd into your debugacademy directory on your laptop and clone the drupal-vm repository from github, storing it in a folder named academyvm.
 - run ```git clone https://github.com/debugacademy/drupal-vm.git academyvm``` 
 - You should see a new folder inside your debugacademy directory named "academyvm". This folder will have many files and subfolders inside of it. "academyvm" stands for "Academy Virtual Machine".

*What we are doing in the next steps is following the installation steps from* https://github.com/debugacademy/drupal-vm#1---install-vagrant-and-virtualbox . This classwork goes through them in significantly greater detail.

3 - Inside the academyvm folder, copy default.config.yml to config.yml. We can use the cp command in terminal/gitbash to do this.
 - Enter the folder: `cd ~/Desktop/debugacademy/academyvm`
 - Copy and paste the file: ```cp default.config.yml config.yml```.

4 - Using terminal/gitbash, install your virtual machine. You will need to do this frmo inside of the academyvm folder, where the file named Vagrantfile is located. 
 - Enter the folder: `cd ~/Desktop/debugacademy/academyvm`
 - Run ```vagrant up```. This command might take a long time.

**Note:** *If there are any errors* during the course of running vagrant up, and it drops you back to your command prompt, *run `vagrant provision`* to continue building the VM from where you left off. If there are still errors after doing this a few times, post an issue to this project's issue queue on GitHub with the error.

5 - Configure your host machine to access the VM.
  - @Debug Academy: add each of the below lines to your hosts file so you can connect to the VM.  
    - ```192.170.88.17  academyvm.dev```  
    - ```192.170.88.17  dev-1.academyvm.dev```  
    - ```192.170.88.17  dev-2.academyvm.dev```  
    - ```192.170.88.17  stage-1.academyvm.dev```  
    - ```192.170.88.17  stage-2.academyvm.dev```  
    - ```192.170.88.17  php.academyvm.dev```  
    - ```192.170.88.17  adminer.academyvm.dev```  
    - ```192.170.88.17  xhprof.academyvm.dev```  
    - ```192.170.88.17  pimpmylog.academyvm.dev```  
    - ```192.170.88.17  dashboard.academyvm.dev```  
       
This file is in different locations depending on your Operating Systems. Instructions for editing your hosts file can be found at https://support.rackspace.com/how-to/modify-your-hosts-file/ .
- For Mac users: Scroll down to the section titled "Mac OS X 10.6 through 10.11". 
- For Linux users: Scroll down to the section titled "Linux".
- For Windows users: Scroll down to the section titled "Windows". 
**Note for Windows users only: Regarding step 4, make sure the browser window allows "All files" and not just "Text Documents (*.txt)" files to be opened. This will allow you to see the hosts file. Be sure to save the file after making changes.**

6 - In your browser, visit http://dashboard.academyvm.dev/. If the setup was successful, you should see an interface that lists several sites. The page will be titled "Drupal VM".
