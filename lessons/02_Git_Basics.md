# Git Fundamentals
---
**_Learning Objectives_:**  
1. Understand why we use version control and Git
2. Learn basic terms used in Git and GitHub, such as clone, commit, push, pull, and merge
3. Learn how to clone repositories, make changes, and update changes on local and remote repositories
4. Handle branches and resolve merge conflicts<br>
 ---
### Icons Used in This Notebook 
🔔 **Question**: A quick question to help you understand what's going on.<br>
🥊 **Challenge**: Interactive excersise. We'll work through these in the workshop!<br>
💡 **Tip**: How to do something a bit more efficiently or effectively.<br>
 ⚠️ **Warning:** Heads-up about tricky stuff or common mistakes.<br>
📝 **Poll:** A Zoom poll to help you learn!<br>
🎬 **Demo**: Showing off something more advanced <br>


## Version Control<br>
🔔**Question**: Have you ever made a mistake of overwriting a file or saving the wrong version?<br>
 
> Imagine that you’re collaborating with one of your labmates on a project. You’re both making changes to a document or a codebase. At one point, you both have changed the same lines in a particular document. How do you go about merging your changes?

This is why we use version control. **Version control** is a system that manages and records changes to files over time. The most commonly used version control system is called **Git** (others include Mercurial and SVN). Git keeps track of the differences in the repository each time you make a change. The entire history of the repository is tracked by Git. If you realize you made a mistake in your code, you can always roll it back to a previous time point.

If you have used Google Docs, you likely have already used version control. Google Docs now tracks every change that every user makes, and allows you to go to any version of the document. Git allows us to do the same thing in complex code environments.

## Git Workflows: Personal Workflow
There are a variety of workflows you may employ when using Git to track your changes. The most common, particularly for academic settings, is the **personal workflow**.

<br><img src="../images/personal.png" alt="forking" width="50%">

In the personal workflow, you are largely going to be the only person adding to the repository. You have one **branch**, or version of your project. It is called the `main` branch. Every time you make changes to the code, you'll add them to the `main` branch. 

The main goal with version control settings is keeping track of the changes that you, the main user, are making to your repository. You don't have to worry about handling multiple people working on the repository at once, which simplifies the workflow. This is the first setting we will work in for this workshop.

## GitHub
Git is often used in tandem with a cloud-based hosting platform - the most common is **GitHub** (but others include Gitlab and Bitbucket). GitHub is a hosting service for Git repositories. It allows you to store your Git projects in the cloud and provides a platform for collaborating with others. The benefit to using GitHub is that it makes it easier to collaborate on code with others via its web platform.<br>
 
In this lesson, we're going to use Git in command line and GitHub to make updates to a repository.  <br>

A **repository** (or repo for short) is a central place where all the files related to a project are stored. It includes your project’s code, documentation, and a record of every change made to the files over time, managed through a version control system like Git. <br>

## Managing Local and Remote Repositories
We need to make a distinction between two kinds of repositories: there's the local repository and the remote repository. **The local repository** is the version of the code that is stored on your computer. **The remote repository**, meanwhile, is any version of the repository that lies on some other machine. In this context, remote repository is almost always going to refer to the version that is on on GitHub's servers. <br>

So, when we're making changes to a repository, there's two versions that need to stay in sync with each other: the local and the remote. The steps we outline keep track of those changes between both cases, while also keeping track of the entire history. GitHub provides a nice platform on which we can peruse the history of a repository.<br>
<br><img src="../images/workflow.png" alt="forking" width="50%"><br>

1. **Commit**: Save your selected changes with a description.
2. **Push**: Upload your saved changes to GitHub for others to see.
3. **Pull**: Download the latest updates from GitHub to your project.

For Git from command line, there are two more command you will use: `add` and `status`
<br><img src="../images/committing.jpeg" alt="forking" width="50%"><br>

Let's go through the process of making changes to a repository, step by step.<br>
 
### 1. **Creating a Repository**
To create a new repository on GitHub, click on this [link](https://docs.github.com/en/get-started/quickstart/create-a-repo) and follow the instructions. Make sure to tick the `Add a README file` box under "Initialize this repository with". Click on `Create repository`. You now have a remote repository (on GitHub's servers), but **not** a local repository.<br>

🥊**Challenge**: Let's create a new repository under your account. <br>

### 2. **Cloning** 
Cloning a repository means taking a remote repository, and copying it to our local machine to create a local repository. We run the command `git clone [REPO-LINK]` to do so, filling `[REPO-LINK]` with the link to your repository.<br>
The terminal will ask for your username and password. Use your Github username as the username and the personal token we created as the password. 

🥊**Challenge**: Let's clone a repository. <br>
💡 **Tip**: In command line (Bash /Zsh), `cd` is used to change directories and `ls` is used to look at the list of files in a directory.

### 3. **Checking the status** 
A useful command to always run is `git status`. This will provide a summary of what's going on in your repo. Run it to see what happens - all it should say is that it's up to date with origin/main: this means that it's up to date with origin, which is its name for the remote repo. Within origin, it's synced to the main branch. <br>

### 4. **Making a Change** 
Let's make changes to the repo. Let's make a change by creating a new file. Create a file called `text.txt`, which has some text in it of your choosing. You can also add a new text file by `touch [text_file_name]`, make new directories, or edit the `README` file.  
<br>
🥊**Challenge**: Let's make changes to your **local** repository.  <br>

🔔**Question**: Do you see these changes on your GitHub? <br>
🔔**Question**: What does it say when you run `git status`? <br>

### 5. **Staging** 
The first step to codifying this change in the git history is to stage it, which is done with the `git add` command. Once a change is "added", it is placed in a staging area. You can think of this as a "proposal" for the next record in the Git history. The proposal is made permanent in the following step. To add the file, `run git add test.txt`. <br>

🔔**Question**: What does it say when you run `git status`? <br>
🥊**Challenge**: what happens if you do `git add --all`. <br>

### 6. **Committing a Change** 
Committing changes entails taking a snapshot of them: once we do this, the changes are frozen and placed in the `git` history. Each commit needs an accompanying message to say what the reason for the commit is. Make sure these messages are informative - your future self will thank you!<br>
Commit the file by running `git commit -m "adding new folders and files"` or any comment you think are appropriate. 

🔔**Question**: What should be our next line of code/command? <br>

### 7. **Pushing to the Remote Repository** 
Right now, the local repo knows about the changes we did, but the remote repo doesn't. So, we need to synchronize the two by "pushing" our changes to the remote repo. We do by `git push origin main`. we are pushing the changes we made to `origin`(the name of the remote repo), on the `main` branch. Interface will ask for your username and password (token). <br>

### 8. Check GitHub
Let's check the GitHub page to see if the changes you made manifest on the website! <br>

### 9. Make Edits and Commits on GitHub Directly
Let's make changes to the remote repository by making changes GitHub page directly. <br>

So, even in the personal workflow, there's a lot of individual steps needed just to make changes to the codebase. This becomes a little bit more complicated when multiple people are making changes at the same time, which requires a slightly different workflow.<br>

💡 **Tip** Do `git pull` before working on a repository so that your local repo is up to date with your remote repo. 


  

