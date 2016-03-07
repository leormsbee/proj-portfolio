# Drupal site building
In this assignment, we will begin building the content blocks for use in phase 1 of the ARCS project.  

Note: a lesson has been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment.  

## Answering questions
For this assignment, you will be committing changes to:  
- hw_007_build_arcs_phase_1.md (the file you are reading)  
- Your proj-arcs repo  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of assignment 6's branch using the following convention:**  
** - [Project]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```arcs-007-aa```  

### Need to know
#### Site isn't working?
If your Drupal site is not loading at all, you may need to run vagrant up from the academyvm folder to ensure your server is running

#### Can't log in to your site?
- SSH into your vagrant environment ('cd' to your academyvm folder, run 'vagrant ssh' from there)
- 'cd' to your website's vagrant path. For example, cd /var/www/dev-2/proj-arcs
- Run: drush uli
- Copy the URL which was output
- Replace the word 'default' in the URL you copied with your site's URL
- Visit the modified URL in your website browser
- You will be automatically logged in

#### How do I run drush commands?
- SSH into your vagrant environment ('cd' to your academyvm folder, run 'vagrant ssh' from there)  
- 'cd' to your website's vagrant path. For example, cd /var/www/dev-2/proj-arcs  
- You can now run drush commands for your website. See our drush lesson in the course-drupal repository for a list of drush commands.  

### Task 0 - Set up
Enable the following modules using drush's ```drush en [modulename]``` command:  
- Views (```views```)
- Views UI (```view_ui```)
- Panels (```panels```)
- Views slideshow (```views_slideshow```)
- @fontyourface (```fontyourface```)
- Administration menu (```admin_menu```)

For example, the 'views' module would be enabled as follows: ```drush en views```  

### Task 1 - Create the homepage
We will create a homepage using the panels module, which will allow us to 'drag and drop' content onto our site's homepage.  

If you enabled the admin_menu module in the previous step, you should now have a drop down black administration menu when logged in as an administrator.  

First, visit your website's homepage, and confirm it says something like: 'Welcome to [site name]'. We are going to replace this page with (initially) a blank page.  

To create the page:  
- Visit structure -> pages -> Create page
- Name the page something self-explanatory, such as 'Homepage'
- Follow the steps. When presented with a layout choice, choose a 1 column layout.
- When presented with the option, choose 'Set as homepage'
  - If you were not presented with the option, please explore settings on the page you are creating.
- Save the page you created.

Now, visit your website's homepage again, and confirm it *no longer* says 'Welcome to [site name]'.  

If it does not, then you either did not save the page after finishing, or did not set your page as the homepage.  

### Task 2 - Add the first section
The first section is simply text saying this:
"
According to the united nations:
Syria is the worst humanitarian crisis in our history.
"

To add this text to your panel page:  
1. Visit your site's homepage while logged in.
2. Hover your mouse over the page's content area, a 'gear' icon should appear in the upper right corner of the page. Click it
3. Click 'Configure'
4. Click the gear icon on the content area of the page you are taken to
5. Click: 'Add content'
6. Click: 'Add custom content'
- Make the content's title: According to the united nations:  
- Make the content's body: Syria is the worst humanitarian crisis in our history.  
- Save the content

Now, save the page, and visit your homepage to confirm the content's placement.  

Write your impression of completing this task here. Did you not understand something you felt was important to this process?  

### Task 4 - Create blog view
This task can be found at the following URL:  
https://github.com/debugacademy/da-assignments/issues/310  

Upon *beginning* a task, please comment at the above URL.  

Write your impression of completing this task here. Did you not understand something you felt was important to this process?  

### Task 5 - Create news view
This task can be found at the following URL:  
https://github.com/debugacademy/da-assignments/issues/311  

Upon *beginning* a task, please comment at the above URL.  

Write your impression of completing this task here. Did you not understand something you felt was important to this process?  

### Task 6 - Create Member organization logos view
This task can be found at the following URL:  
https://github.com/debugacademy/da-assignments/issues/312  

Upon *beginning* a task, please comment at the above URL.  

Write your impression of completing this task here. Did you not understand something you felt was important to this process?  

### Task 7 - Place view panes on the homepage
The prior tasks *must be completed* before this task is started.  

For our March 15th launch, the homepage must contain the following sections:
- Homepage Slideshow
- Custom text pane
- Map pane
- Newsletter block
- Making an impact custom pane
- First blog post
- Following 3 blog posts
- News items
- Member organization logos
- Place donation + save lives pane

We will be placing a few of those sections on our homepage.  

Edit the homepage panel page:  
1. Visit your site's homepage while logged in as administrator.
2. Hover your mouse over the page's content area, a 'gear' icon should appear in the upper right corner of the page. Click it
3. Click 'Configure'

Add the view panes you have created for the homepage:  
1. Click the gear icon on the content area of the page you are taken to
2. Click: 'Add content'
3. Choose the category 'view panes'
4. Select the view pane you would like to place

Remember to place the content in the appropriate order, because this is how it will appear on the homepage. For now, only place the content that is available to you - skip sections that are not, such as 'Place donation..'  

Remember to press 'save' after completing this work.  

### Task 8 - Thoroughly test each section
In task 7, you should have placed at least the following views:  
1. First blog post
2. Blog posts 2-4
3. News items 1-3
4. Member org logos

However, after placing these views and visiting your homepage, you may notice that the views do not appear. If so, this is most likely because there are no blog posts, news, or member organizations.  

To properly test our homepage, we must:  
1. Create 5 blog posts, to ensure the first 4 appear properly.
2. Create 4 news posts, to ensure only the first 3 appear.
3. Create 6 member organizations, attaching a logo to each one, to ensure only the logos appear

Once this content is created, we should test to verify that everything we created is functioning as planned.  

To create content, visit Content -> Add content using your site's administration menu (the black bar on top).  

For example:  
- One blog post should display in the first view
  - The blog post should have a 'Read more' link
- Three blog posts should display in the second view
  - The first blog post should not be included in the second view

### Task 9 - Export your work to features
To submit your updates to the website, you will need to export them to features.  

First, download and enable the features module if you have not already done so.  

#### Create a Common Fields feature
- Create a new feature (Structure -> Features -> Create new feature)
- Name the feature something like: ARCS Common Fields
- Select *only* the 'field bases' for every field you have added
- This ensures all of your field bases will be stored in 1 feature, so they do not conflict

#### Create a feature for ARCS' core functionality
- Create a new feature (Structure -> Features -> Create new feature)
- Name the feature something like: ARCS Core
- Select everything you created from assignment 6 and assignment 7
  - For example, select each content type you modified
  - And select the panel page (homepage) you created
  - And select each view you created
  - And select the newsletter module you are using as a dependency
- Explicitly *uncheck every field base* from this feature
  - Do not uncheck field instances
- Add your ARCS Common Fields feature as a dependency
  - That ensures the field bases your feature needs will be enabled  

Commit every module (including contributed and custom modules). Each module should be in its own commit. Then, submit a pull request from your proj-arcs repository with your work.  
