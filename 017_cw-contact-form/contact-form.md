# Drupal site building
In this assignment, we will download and configure a Drupal module that will allow us to create a contact form where users can contact us.

## Answering questions
For this assignment, you will be committing changes to:  
- Your local proj-me repository

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

Before beginning, you must cd into debugacademy/academyvm and run ```vagrant up```. After that, run ```vagrant ssh``` and cd into your `/var/www/dev-1/proj-me` directory.

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Use the currently checked out branch in the proj-me repository**  

### Task 1 - Research which Drupal 8 module to use for creating a contact form
Our site will feature a contact form that users will be able to submit to ask us questions or leave comments. We must determine which module we will use to create our contact form.
- Search google for a Drupal 8 module which provides this functionality.
- The modules you find must be located on drupal.org.  
- The modules must have a Drupal 8 version

To determine which module is best, compare information such as: 
- What does the module's description say
- How many downloads the module has
- How stable is the D8 version (dev, alpha, beta, full release)
- When was the module last updated
- How many D8 bugs does the module have (in the issue queue)

Pick the module which you think will best accomplish this task.

Once a module is selected:
Record the 'machine name' of the module. It is the module name from the drupal.org URL - the portion of the URL *after* drupal.org/project/

### Task 2 - Download and enable the module you chose
- Inside of vagrant (vagrant ssh then cd into `var/www/dev-1/proj-me`), run `composer require drupal/MACHINE_NAME_OF_DRUPAL_MODULE_HERE` . This command will automatically download the module and place it into the proj-me/web/modules/contrib folder.  
- Next, you must log in to your Drupal website as an administrator (`http://dev-1.academyvm.dev/proj-me/web`) . Click 'Extend' in the top administration bar. Search for the module you downloaded, then enable it as well as any of its dependencies.

### Task 3 - Create and configure the contact form
- Navigate to Structure and you should see the module that you downloaded. Click on it to open its admin interface.
- Add a new form and name it "Contact".
- You can add fields to the form by clicking on "+Add element". We need the following fields to be added to the form:
  - Name (Text field) 
  - Email (Email field)
  - Phone (Telephphone field)
  - How did you find me? 
    - This will be a field of the "Select" type. You should add the following options:
      - drupal.org
      - Search Engine
      - Recommendation
      - Meetup
      - Other

### Task 4 - Add a "Contact" menu item
- To do this, we will need to know the URL of the contact form. To get the URL of your contact form, click on "View". Copy the relative URL of the contact form - the portion of the URL *after* http://dev-1.academyvm.dev/proj-me/web
- Navigate to Structure » Menus » and click on "Edit menu" to the right of "Main Navigation".
- Click on +Add Link and add a link titled "Contact" and give it the link path you found from the first step of this task. 
- Navigate to the homepage and you should see a new menu link titled "Contact". Once you click on it, you should see your contact form!

### Task 5 - Export your website's configuration
- You should already have a folder in your proj-me directory called "config". As mentioned in previous assignments, this is where we will place all of our configuration exports. 
- On your drupal site, navigate to Configuration » Configuration synchronization » Export. The full url will be 'http://dev-1.academyvm.dev/proj-me/web/admin/config/development/configuration/full/export'.
- Click on the "Export" button. This will download a file that contains all the work you've done on the website this far. The file will be saved to your downloads folder. 
- Move the exported file to the sites/dev-1/proj-me/config folder on your computer.
- Outside of vagrant, Run git status to see which files have been added or modified
- Outside of vagrant, Git add and commit the composer.lock and composer.json files in one commit
- Outside of vagrant, Git add and commit the configuration file in your new config folder in another commit

## Submitting your assignment

### Step 1
Push the branch you created for this assignment to your fork of the proj-me repository (e.g. git push [remote-name] [branch name]).

### Step 2
Create a pull request to the proj-me repositiory on github. Once you visit the main proj-me repository on github (https://github.com/debugacademy/proj-me), you should see a notification indicating that you had just pushed a branch. There should be a green "Compare and Pull Request" button).
