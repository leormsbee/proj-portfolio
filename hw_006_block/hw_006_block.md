# Homework - Creating a Block
In this homework assignment, we will use Drupal to create a block that will contain some HTML.

## Answering questions
For this assignment, you will be committing changes to:  
- Your proj-themes repo

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```block-006-aa```  

### Download and enable the features_extra module.

- cd into your proj-themes folder and run ```drush dl features_extra -y```
- This module actually contains a sub-module named fe_blocks, which should be enabled: `drush en fe_block -y`

This module will allow you to export blocks with features, and add machine names to blocks in features.

### Create the "Designs Info" block.
Navigate to Home » Administration » Structure » + Add block
- Fill in a Machine Name for the block. Machine names should start with a letter and only contain letters and underscores. A good machine name would be `designs_info`.
- Fill in the Block Title field. This will be displayed to users. Enter `Our designs are coded by graduates of our class`.
- Assign the block a description. This is only displayed to developers. 'Homepage Design Info' is a good description for the block.
- Under the 'Body' field, change the Text format to from Filtered HTML to **Full HTML** and include the following HTML inside the block body:

```
     <span>Your purchase is supporting scholarships for students</span><br>
     <a href="#" class="button">Learn More</a>
```
- Inside the block, we created a span a sentence and a link inside.
- Save the block. You will now export this block to a feature.

### Add your newly created Designs Info block to the "Athemes Core" feature.
- Navigate to Home » Administration » Structure » Features and open the Athemes Core feature. It was created during classwork assignment 4.
- Find the block you created on the right side and check it off.
- Under Advanced Options, click 'Generate feature'
- Git add and commit the updated feature

## Submitting your assignment
### Step 1
Push the branch to your fork of the proj-themes repository (e.g. git push `<remote-name>` `branch-name`).

### Step 2
Create a pull request for the branch.
