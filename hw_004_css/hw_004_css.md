# Image to HTML and CSS
In this assignment, we will continue our work on coding the design for Continuous Good. In hw #3, each student submitted an HTML-only version of the design. We will now begin coding the CSS to accompany the HTML. To ensure we all are starting from the same point, one hw3 submission was selected and can be found in the hw_004_css folder at continuousgood/homepage.html.

> Continuous Good is a web application that aims to solve the problem of wanting to give charitable donations to so many different causes, and not being able to decide which one(s) to donate to. The goal is to subscribe to causes and organizations, to set a monthly amount to donate, and for the website to handle the rest. Each month, you will receive an email informing you of how that month's donation will be helping people.

## Answering questions
For this assignment, you will be committing changes to:
- hw_004_css.md (the file you are reading)
- continuousgood/homepage.html
- continuousgood/style.css

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create a branch for question 2 only. It should be based off of the master branch, using the following convention:**  
** - [Topic]-[Assignment Number]-[Question Number]-[Your initials]**  

Ashraf Abed would create a branch named: ```css-cg-004-2-aa```

1- Complete the following CSS tutorials:
- Every lesson until 'CSS Attr Selectors': http://www.w3schools.com/css/css_intro.asp
- All 19 steps/pages: http://learnlayout.com/display.html
- Choose one (or many) additional tutorials that you found to be beneficial as you learn CSS. Post a link to this tutorial in the students channel in slack so that your peers may benefit as well.

Open the continuousgood folder. It contains several files that will be necessary for working on this assignment:
- continuousgood.jpg: this is the image of the continuous good homepage design that you will base your HTML and CSS off of.
- images: this is a folder with images you will need as you adjust your HTML and write your CSS for the homepage design.
- homepage.html: this is the html file you will be you refining and committing changes to.
- style.css: this is the CSS file you will be modifying and committing changes to.

2- Code the continuous good homepage's CSS to accompany the HTML in continuousgood/homepage.html. 

**Commit often, clearly, and concisely.**

Open the continuousgood.jpg file. It is an image of the homepage design for the Continuous Good site. Looking at the design at a high-level, we can split it up into different sections. The logo and the menu together make up one section, known as the header. The section containing the main background image in this design can be referred to as the 'hero'. We'll refer to the remaining sections as Section 1, Section 2, etc, all the way up to the Footer.

----------
Header
----------
Continuous Good logo on left
- image for logo can be found at images/header.jpg

Menu to the right
- The links' text color should be: #40a2c9
- The links' text background should be: white
- The hovered links' text color should be: white
- The hovered links' background color should be: #8ccae3

----------
Hero
----------
Main image
- images/Head-StockPhoto.jpg

Dummy text on top of main image

Give Forward button on top of main image
- images/button-givefwd.png

----------
Section 1
----------
Text: One action, continuous good

Background image for entire section: images/lightgray-bg.gif
- ONLY repeats horizontally
- Background image aligned at the bottom of the div
- Background color for entire section: #ffffff

Background image for the 3 large circles: images/circle-section1.png  

Inner-circle images:  
- images/circle-icon-check.jpg
- images/circle-icon-cal.jpg
- images/circle-icon-heart.jpg

Background image for the 3 smaller circles (#1, #2, #3): images/circle-section1.png

----------
Section 2
----------
Welcome to continuous good
Background Image: images/section-2-top-dotted-border.jpg
- ONLY repeats horizontally
- Background image aligned at the top of the div
- Background color's Hex code: #3eada7

----------
Section 3
----------
Step 1
Image: images/section-2-top-squiggle-border.jpg
- ONLY repeats horizontally
- Background image aligned at the top of the div
- Background color's Hex code: #fdfdff

You *can* use the same image for each block in this section.

Items:
"Collapsed" - images/purple-cause-prehover.png
"Expanded" - images/purple-cause-hover.png
Cause image: Use any image from google - does not need to be blurred.

----------
Section 4
----------
Step 2

Background Image: images/hands-bg.jpg

----------
Section 5
----------
Testimonials

----------
Section 6
----------
Step 3
Background Image: images/section-2-top-dotted-border.jpg
- ONLY repeats horizontally
- Background image aligned at the top of the div
- Background color's Hex code: #3eada7

Submit button's background hex color: #2fde91

----------
Section 7
----------
Newsletter
Background Image: images/section-2-top-squiggle-border.jpg
- ONLY repeats horizontally
- Background image aligned at the top of the div
- Background color's Hex code: #fdfdff

## Submitting your assignment
Up until this point, you should have one branch of work (question 2).

### Step 1
Push the branch to your fork of the da-assignments repository (e.g. git push <remote-name> csscg-004-2-mk).

### Step 2
Create a pull request for the branch.
