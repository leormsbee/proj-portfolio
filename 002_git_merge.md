# Intro to Git
In this assignment, we will get more comfortable resolving git conflicts.

## Answering questions
For this assignment, you will be committing changes to 001_git.md, as well as a change to the file you are reading now, 002_git_merge.md. Your answers will be submitted as a pull request on github.  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be your own work**  

## Committing
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.

## Questions
**Create an integration branch based off of the master branch using the following convention:**  
** - [Topic]-[Assignment Number]-[Question Number]-[Your initials]**  

*For example, for question 1:*  
Ashraf Abed would create a branch named: ```integration-002-1-aa```  

1- Merge all of the following into your integration branch:
- All of the branches you created for homework assignment #1
- A classmates' branches from homework assignment #1
- Another classmates' branches from homework assignment #1

**Note: if a window appears upon merging with a message like `Merge remote-tracking branch...`, press the `escape` key, then type `:wq`, then press the `Enter` key.**

There are a few steps that must be done for this question.  
You will need to:
- Read the lesson on git commands:
  - https://github.com/debugacademy/da-lessons/blob/master/005_git_commands.md
- Keep that lesson open as a reference during the homework
  - Each of the following steps is described in the lesson
- Add your classmates' assignment repos as remotes
  - Allows you to 'talk to' their repos
  - In this case, allows you to fetch their branches
  - Like adding a name & phone number to your cellphone
- 'Fetch' from your classmates' repos
  - Downloads copies of all of their branches to your computer
- Merge each branch, one by one, into your integration branch
  - **Note: if a window appears upon merging with a message like `Merge remote-tracking branch...`, press the `escape` key, then type `:wq`, then press the `Enter` key.**
  - Must be on the integration branch while merging
  - Must use branch names displayed when 'git fetch' is performed
    - Including the 'name/' portion of the branch name
- Resolve merge conflicts as they arise.
**Create a pull request from your integration branch**  

2- Create an integration-rebased branch, whose history initially matches that of your integration branch. AKA: Create a branch named ```integration-rebased``` based off of your integration branch from question 1.  
- Rebase the new branch onto the debugacademy repo's 'develop' branch.  
  - This will update your integration-rebased branch
  - It will place the commits from your integration-rebased branch *after* the commits on the develop branch
  - **Any time there is a conflict, it will stop rebasing and tell you to resolve the issue**
  - **Conflicts are resolved the same way they were with merge conflicts**
  - After resolving conflicts, `git add` the file(s), then type `git rebase --continue` to resume the rebase process
- Submit a pull request for your integration-rebased branch.  

**Questions 3, 4, 5, and 6 should be on a branch of their own.**
**The branch should be based off of develop.**
**Submit a single pull request for the branch.**

3- Explain, in plain English, the solution to question 1. Include what we were doing, and how we did it. Commit your answer to this question in its own commit.  
**Type your answer to question 3 right here.**

4- Explain, in plain English, the solution to question 2. Include what we were doing, and how we did it. Commit your answer to this question in its own commit.  
**Type your answer to question 4 right here.**

5- Explain how you would create a new branch based off of develop. Include the command(s) you would use.
**Type your answer to question 5 right here.**

6- Explain how you would switch branches in plain english, including the command used.
**Type your answer to question 6 right here.**
