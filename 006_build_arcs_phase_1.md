# Drupal site building
In this assignment, we will begin building the content architecture phase 1 of the ARCS project.  

Note: a lesson has been posted in the course-drupal repository on Drupal site building. It contains relevant information to this assignment.  

## Answering questions
For this assignment, you will be committing changes to:  
- 006_build_arcs_phase_1.md (the file you are reading)  
- Your proj-arcs repo  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Questions
**Create a branch based off of assignment 6's branch using the following convention:**  
** - [Project]-[Assignment Number]-[Your initials]**  

*For example, for this assignment:*  
Ashraf Abed would create a branch named: ```arcs-006-aa```  

### Task 1 - Set up Blog content type
Goal: Set up the infrastructure for creating blog posts

The ARCS organization would like to create blog posts on their website. Each blog post has a title, a message (body), and an image. We would like to create a content type so users can easily add member organizations to the website. Content of the same type is created using a single 'content type', and shares the same fields.  

For example:
- Each Blog post has a 'Title'
- Each Blog post has a 'body' field, storing rich (formattable) text
- Each Blog post can have an 'image'

Let's see if we have any content types that accomplish what we are looking for.

1. Log in as admin
2. Click 'Structure'
3. Click 'Content types'

One of the content types looks promising for creating blog posts. Let's see what fields it has.

Click 'manage fields'. I see 'Title' and 'Body' fields. That covers 2/3 of the fields we said we needed.

Now, **add the image field to the content type**, if it does not exist.

Afterwards, edit the 'Article' content type. Rename it to 'Blog post', and read the rest of the settings to determine whether they need to be updated.  

Be sure to create blog posts for testing! Go to Content > Add content to create new content. You can always delete test content.  

### Task 2 - Set up Member Organization content type
Goal: Set up the infrastructure for displaying member organizations

The ARCS organization has about 20 member organizations. Each member organization has a logo, a location, a mission statement, and more. We would like to create a content type so users can easily add member organizations to the website. Content of the same type is created using a single 'content type', and shares the same fields.  

- Each Member organization has a 'Title' property (property is provided by Drupal automatically)  

Fields:  
- Each Member organization has a 'Mission' field, storing rich (formattable) text
  - Use the existing 'body' field for this
- Each Member organization can have a 'logo' image field  
- Each Member organization can have a 'location' field storing their address  
  - Research and choose a module which provides a field for storing an address or location  

Let's see if we have any content types that accomplish what we are looking for.

1. Log in as admin
2. Click 'Structure'
3. Click 'Content types'

This is not a content type that most websites will have, so we will need to create a new content type.

When complete, be sure to create member organizations for testing! Go to Content > Add content to create new content. You can always delete test pages.

### Task 3 - Set up News content type
Goal: Set up the infrastructure for displaying simple news items

In addition to blog posts, ARCS would like the ability to link to news snippets, including external links.  

The news content type should include:
- A title  
- An optional external link  
- A 'body' field  

When complete, be sure to create news items for testing! Go to Content > Add content to create new content. You can always delete test pages.  

### Task 4 - Set up Event content type
Goal: Set up the infrastructure for creating events

The ARCS organization will have events. Each member organization has a logo, a location, a mission statement, and more. We would like to create a content type so users can easily add member organizations to the website. Content of the same type is created using a single 'content type', and shares the same fields.  

- Each Event has a 'Title' property (property is provided by Drupal automatically)  

Fields:  
- Each Event has a 'Description' field, storing rich (formattable) text
  - Use the existing 'body' field for this
- Each Event can have a 'Banner' image field  
- Each Event can have a 'location' field storing their address  
  - Use the same field type you used for the member organization address or location field  

Let's see if we have any content types that accomplish what we are looking for.

1. Log in as admin
2. Click 'Structure'
3. Click 'Content types'

This is not a content type that most websites will have, so we will need to create a new content type.

When complete, be sure to create events for testing! Go to Content > Add content to create new content. You can always delete test events.

### Task 5 - Add a newsletter
This website will have a newsletter sign up form in the footer. The newsletter will accept an e-mail address only, and the module should provide the newsletter in a block.  

#### Task 5.1 - Determine approach
Research options for adding a newsletter to a Drupal website.

What are the top implementation options based on your research?
  - **Write answer here**

Which option do you recommend, and why?
  - **Write answer here**

#### Task 5.2 - Add the newsletter to the footer
Using your answer from 5.1, download and enable the appropriate newsletter module from Drupal.org.  

Once enabled, visit Structure -> Blocks, and place the newsletter block in the theme's footer region. When complete, clear the Drupal cache and visit your homepage to confirm the newsletter block appears in the footer.  
