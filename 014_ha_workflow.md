# HA Backend
In this assignment, we will build the structure for HA Lighting's primary content and user roles.  
  
Note: material for this assignment spans a number of lessons. Primarily, site building and entities fields and properties.  
  
## Answering questions  
For this assignment, you will be committing changes to:    
- 014_ha_workflow.md (the file you are reading)    
- Your proj-ha repo (you should be able to access it using the shortcut at symlinks/halighting)  
  
**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**    
  
## Committing  
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.    
  
## Questions  
**Create a branch based off of the master branch using the following convention:**    
** - [Topic]-[Assignment Number]-[Your initials]**    
  
*For example, for this assignment:*    
Ashraf Abed would create a branch named: ```ha-workflow-014-aa```    
  
### Task - Set up user roles  
Add/create the following (user) roles:  
- Client  
- Office Assistant  
- Technician  
- Technician Supervisor  
- Leader  
- Developer  
  
Leave all with default permissions for now.  
  
Export these roles to a feature named: ha_backend  
As always, the feature should be placed in sites/all/modules/custom/  
  
Commit the new feature, stating that it contains our user roles.  
  
### Task - Download & commit modules  
As always, each module must be committed in its own commit. We will be using each of the following modules.  

Note the time you start working on this task.  

- field_permissions  
	- Allows setting user permissions on a field-by-field basis. Great for restricting specific fields without having to create a new content type  
- entityreference (CER)  
	- A field type which allows connecting, or 'referencing', entities of any type  
- corresponding entity references (CER)  
	- Allows for automatically populating 'mirror' entity reference fields to create 2-way relationships between content  
- inline entity form  
	- Allows entity reference fields to display the entire entity form for an entity being referenced.  
- workbench moderation  
	- Provides role-based workflow management, such as moving content from draft -> in review -> published.  
- views_ui  
	- Comes with the views module  
	- Exposes the UI for editing and creating views  
- admin_menu  
	- Provides a significantly better administrator menu  
- panels  
	- Allows creating pages and placing content on them  
	- We will be using this to create the homepage, and many other pages  
- rules  
	- Comes with the rules_ui module  
	- *You must enable rules_ui to see the UI for the rules module.*  
	- Provides a UI for performing much of what would usually be done by writing custom code  
- devel  
	- Great module for debugging issues on your drupal website. Should not be enabled on prod.  

*Add all of these *EXCEPT* views_ui, rules_ui, and devel as dependencies to your ha_backend feature.*  
About how long, rounded to the nearest half hour, did this task take you to complete? *Write your answer here.*  

Update your feature, and commit these additions in a new commit.  
  
### Task - Module selection  
Because different users have different roles, we will be creating a landing page per user. Research and select a module which allows us to redirect users to specific pages based on which role they are in.  
  
*Write the name of the module you have selected, and why, here.*  
  
*Download and commit the module, then create a pull request for your work so far.*  

### Task - Create the following content types:  
Note: Many of the content types use entity reference fields which rely on content types that are not yet created. Simply *skip the entity reference fields until the content types are available*, and keep a record of fields you still need to implement.  
  
1. Contact  
	- Auto-generate node title  
		- See 'Automatic Entity Label' module  
		- Auto-set title to 'first name + last name' fields  
	- pathauto: contact/[node id]  
		- replace "[node id]" with correct syntax (token) for the node's ID  
	Fields:  
	- First Name  
	- Last Name  
	- Job title  
	- Stores representing  
		- Entity reference   
		- Points only to store nodes  
		- Can have multiple values  
	- Client  
		- Entity reference  
		- Points to Client content type  

Now that you've created the first content type, add it to your ha_backend feature, and commit the updates. *Remember, field bases must only be committed to the ha_common_fields feature. Remove them from this feature if they have been added in.* Field instances, rather than bases, still get added to this feature.  
  
2. Store  
	- Rename 'title' label to 'Store Location #'  
	- pathauto: store/[title]  
	Fields:  
	- Address: US or puerto rico  
	- Store Phone #  
	- Store Contact  
		- Entity reference  
		- Points to 'Contact' type  
		- Can point to existing contact  
		- Can create new contact on the spot  
			- See inline entity form module, or others  
		- CER: store:contact <-> contact:stores  
	- Client  
		- Entity reference  
		- Points to client content type  
		- Store can only have 1 client  

Again, you have finished creating a content type. Update your feature, and create a new commit with the updates. Do this for the upcoming content types, as well.  

3. Client  
	- Rename 'title' label to 'Client name'  
	- pathauto: client/[title]  
	Fields:  
	- Contacts  
		- Entity reference  
		- Points to 'Contact' content type  
		- CER: client:contacts <-> contact:client  
	- Stores  
		- Entity reference  
		- Points to 'Store' content type  
		- CER: client:store <-> store:client  
	- Users  
		- Entity reference  
		- Points to users with role 'Client'  
  
4. Material  
	- Rename 'title' label to 'ID'  
	Fields:  
	- Name  
	- Provided by client?  
		- Checkbox, true/false  
		Field Permission:  
			- View: all  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Purchased by  
		- List field, options are:  
			- HA Lighting  
			- Technician  
		Field Permission:  
			- View:   
				- Office Assistant  
				- Technician  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Charged  
		- Float  
		Field Permission:  
			- View:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Cost  
		- Float  
		Field Permission:  
			- View:   
				- Office Assistant  
				- Technician (view own value only)  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician  
				- Technician Supervisor  
				- Leader  
				- Developer  
  
5. Hourly rate  
	- ID:  
		- Automatically = "Client name : Location zip"  
	- Location  
		- Entity reference  
			- Points to *existing* store location nodes  
		- Required field  
	- Client  
		- Entity reference  
		- Points to client nodes  
		- Required field  
	- Labor hourly rate  
	- Travel hourly rate  
	- Helper hourly rate  
  
6. Job  
	Pathauto: job/[node ID]  
		- Note: syntax is an example, replace with correct syntax  
  
	Fields:  
	- Store serviced  
		- Entity reference  
		- Points to only stores  
			- Can point to existing store  
			- Can create new store on the spot  
				- See inline entity form module, or others  
		- Does NOT accept multiple values. only 1  
	- Contacts  
		- Help text: Place primary contact first.  
		- Entity reference  
		- Reference contact content type  
		- Can reference existing  
		- Can create new  
	- Invoice all contacts?  
		- Checkbox, true or false  
		- Label: Send invoices to all job's contacts?  
	- Emergency job  
		- Checkbox, true or false  
	- Location  
		- Entity reference  
		- Store location content type  
		- Only can add *existing* store locations  
		- Only 1 location can be picked  
	- Service date  
		- Date field  
		- Can pick dates in the future  
		Field Permission:  
			- View: all  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Follow up date  
		- Date field  
		- Needs to default to blank, or null  
		- Can pick dates in the future  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Quote  
		- Float (decimal number)  
		- Estimate sent to the client in an email  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Not to exceed  
		- Float (decimal number)  
		- Is amount the project is not allowed to exceed  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Hours worked  
		- Float (decimal)  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Technician  
		- Entity reference  
		- References users  
			- with role 'technician'  
			- or role 'technician supervisor'  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Internal note  
		- Entity reference  
		- Points to 'note' entity type  
		- Allows multiple values  
		- Only allows creating new value		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Technician  
				- Leader  
				- Developer  
	- Public Update  
		- Entity reference  
		- Points to 'note' entity type  
		- Allows multiple values  
		- Only allows creating new value		Field Permission:  
			- View: all  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Job Forms  
		- File field  
		- Allows multiple attachments  
		- Allows: pdf, doc, docx, jpg, jpeg, png, gif. Anything else?  
		Field Permission:  
			- View: all  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Internal files  
		- File field  
		- Allows multiple attachments  
		Field Permission:  
			- View:  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:   
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Client files  
		- File field  
		- Allows multiple attachments  
		Field Permission:  
			- View:  
				- Client  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:  
				- Client  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
	- Job files  
		- File field  
		- Allows multiple attachments  
		Field Permission:  
			- View:  
				- Technician  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
			- Edit/populate:  
				- Technician  
				- Office Assistant  
				- Technician Supervisor  
				- Leader  
				- Developer  
  

### This marks the end of part 1  
You are expected to complete everything above this line on your own. As always, questions on slack are welcome. The below questions will be addressed in class.  

### Advanced - Create custom entity types  
*This is an advanced task expected of senior developers, you are welcome to attempt it but it is not required.*  
  
https://www.drupal.org/node/1026420  
Instead of using an entity of type node by creating a content type, create a new entity type 'Note':  
  
Note  
	Properties:  
	- Body  
		- Long text field  
	- Date  
		- Date field  
		- Defaults to current time  

Create this entity type in your ha_core custom module. You will likely need to add the entity type initialization code to both an install hook, and an update hook, because the module will likely have already been installed by the time this change is committed.  

### Task - Create basic custom module  
Create a module for HA Lighting. The module will eventually contain our custom code, as well as dependencies, ideally allowing us to 'rebuild the site' simply by enabling this module.  
  
The module should be placed in:  
- sites/all/modules/custom/ha_core  
  
It should contain the files:  
- ha_core.info  
- ha_core.module  
- ha_core.install  
  
The ```.info``` file should contain a minimum of the module's name, version (7.x-1.x), and a brief description.  
  
The ```.module``` file, initially, can simply contain the following:  
```  
<?php  
```  
Note: If the entire file is in PHP, without any gaps, it is encouraged to write the opening PHP tag ```<?php``` without the closing PHP tag ```?>```, as we're doing here.  
  
The ```.install``` file, initially, can simply contain the following:  
```  
<?php  
```  
Note: If the entire file is in PHP, without any gaps, it is encouraged to write the opening PHP tag ```<?php``` without the closing PHP tag ```?>```, as we're doing here.  
  
To test that your module was created successfully, you should be able to enable it using drush without any errors. Run ```drush en ha_core``` to install and enable your module.  
  
Commit this custom module to your codebase.  

### Task - Make basic custom module useful  
The task consists of making the following true:  

When your module is enabled, the following automatically happen:  
- ha_lighting theme should be enabled and set as the default theme  
- ha_public_pages should be enabled  
- ha_backend should be enabled, if it exists  
- Core blocks are enabled/disabled and placed as desired  
- Use drupal's variable_get and variable_set functions to initialize a variable named 'ha_backend_prod' to 0, if it was empty.  
- Enables rules_ui, views_ui, and devel, *only if* the variable ha_backend_prod == 0. (Use variable_get to check the variable's value)  
  
This should all be done in a hook_enable function, placed in ha_core.install, using PHP.   
1. Research how to create the hook_enable function (specifically, what parameters / arguments does it accept). This can be found in the Drupal 7 API.  
2. Research how to programmatically enable a theme and make it default  
3. Research how to use variable_get and variable_set  
4. Research how to programmatically enable modules  
  
The answers to those questions should give you the information you need to create your update hooks.  

About how long, rounded to the nearest half hour, did this task take you to complete? *Write your answer here.*  
  
### Task: Patch field permissions module  
There is a patch on drupal.org, in the field_permissions issue queue, which improves 'Features' integration for the field permissions module.  
  
0. The field permissions module should already be contributed to your repository.

1. Find the patch, and paste a link to it on drupal.org here:  
  
2. Download or copy the patch file then place it in a folder named /patches. For example: halighting/patches/name-of-patch.patch

3. SSH into vagrant, then ```cd``` into your HA Lighting's *field permissions* module folder.

4. Run ```patch -p1 < [relative path to patch file]```
  - Replace [relative path to patch] with the relative path to the patch file you just downloaded, from the directory you are currently in (field_permissions).  

If step 4 was done correctly, it should say that the patch applied successfully.  
  
### Rule: Notify on Follow up date 
This cannot be done until all content types are created.

#### Create a view which:  
- Is named: Jobs needing follow up  
- Shows nodes of type 'job'  
- Has a relationship to the contacts on the contact entity reference field  
- Shows the fields:  
	- Invoice all contacts  
	- Contact email (using the relationship)  
  
Only shows nodes:  
- Where the follow up date field is not empty  
- And where followupdate is in the past (is before now)  
  
- Accepts a contextual filter of node ID  
	- If not given, shows all results  
  
#### Create a rule which:  
- Runs on cron  
- Loops through results of the view you created  
- Checks if the 'Invoice all contacts' field was empty  
	- If empty, it sends 1 email  
	- If not empty, it sends 2 emails  
	- You can send emails to specific email addresses (ashrafabed@gmail.com and your own for testing)  
  
