# GitHub Workflows: Collaborative Workflow <br>

In the collaborative workflow, multiple people may be working on the same repository at the same time. So we need to have a system in place for how to decide whose changes to add, and how to handle scenarios when changes may clash with each other.<br>
 
Collaborative workflows heavily rely on **branching**. A branch in Git (and GitHub) is a separate line of development within a repository. It allows you to work on new features, bug fixes, or experiments without affecting the main codebase. We've already seen this terminology in the context of the `main` branch. <br> 
 
Now, we might be interested in adding a new feature to a code repository. When working collaboratively, we create a **branch** off the `main` repository. This branch can be updated in parallel, without modifying the `main` branch. When we've committed all the changes to the feature branch, how do we go about incorporating them into the`main` branch? <br>

 **Forking** in GitHub is the process of creating a personal copy of someone else's repository in your GitHub account. It allows you to freely make changes without affecting the original repository. <br>
* **Branches** are within the same repository. Branches make it easier collaboration among team members who have access to the repository. <br>
* **Forks** create a completely separate copy of the repository, which is useful for outside contributors.

<br><img src="../images/collaborative.png" alt="forking" width="50%">
 
### 1. **Forking the Repository** 
An extra step you can take when working on a collaborative repository is to **fork** the repo. This creates a copy of the repository on your own GitHub account, which you're free to change at will. You can still, however, pull changes from the original repo, and make pull requests with your own changes. Go ahead and fork the repo [`Git-Playground`](https://github.com/dlab-berkeley/Git-Playground). See the image below for where to find the button:<br>
<img src="../images/fork.png" alt="forking" width="50%"><br>

### 2. **Cloning** 
Cloning a repository means taking a remote repository, and copying it to our local machine to create a local repository. For this section, clone the forked repo of `Git-Playground` to your local machine by using the command `git clone [Link to forked repo]` <br>

### 3. **Branching** 
Create a new branch on your local machine using the command `git branch [branch-name]`. Choose a branch name that feels appropriate to you. This only creates a new branch and does not move you to the new branch. `*` indicates your current branch, the branch you are on. In order to check what branches exist in the repo, use `git branch`. In order to move to the new branch, use `git checkout [branch-name]`. <br>
 
### 4. **Commit a Change** 
🥊 **Challenge**: Create a new file with some text, stage it, and commit it.<br>

### 5. **Push the Change** 
🥊 **Challenge**: Push the change on this branch to your remote repo. <br>

### 6. **Make the Pull Request** 
To merge our changes into the original repository, we do a **Pull Request** (PR). In a PR, we are requesting the `main` branch to pull the changes from the feature branch into the `main` branch. 

GitHub provides a very nice platform to handle PRs - users can view the PRs, comment on them, and ask for changes. Once the maintainer of the repo is satisfied, they can merge the PR and the `main` branch is updated with the changes in the feature branch.<br>
 
The process of merging the changes in this way allows people to work in parallel on the `main` repo without modifying the `main` branch. Couple this with GitHub's platform for handling PRs, and you have a powerful tool for incorporating parallel changes into a repository.<br>
 
Go to your forked `Git-Playground` repository on GitHub. GitHub can already tell you made a change, and gives you the option to make a pull request! Click `Contribute` andn `Open pull request`. If you don't see this button, no worries - go to the "Pull Requests" button next to Issues, and you can manually make one there. Follow the instructions for making the pull request, and we'll merge a couple of them!<br>

🎬 **Demo**: We will try to respond to a "Pull Request" with a conflict with changes I made. 

# Removing git repositories<br>
 
* **Local:** If you want to delete local git-related information (like  branches and versions), all you have to do is delete the `.git` directory in  the root-directory of your repository. Note that `.git` directories are hidden  by default, so you'll need to be able to view hidden files to delete it.  If you want to delete everything (data, code, etc.), just delete the whole  directory.<br>
 
* **Remote:** If you want to delete a remote repository, navigate to GitHub and go to Settings, then Danger Zone (at the bottom of the Settings page). Warning:Once you delete a repository, there is no going back.<br>
 
# Key Points
 There are several different workflows in which you might imagine using `git` and `GitHub`, particularly in an academic setting. These include:<br>
 
1. Working on a repository that is your own repo. You expect that you will generally be the only person developing code for this repository. <br>
2. Working on a repository that several people - perhaps some collaborators - are working on concurrently. <br>
3. Working on a repository that *many* people (e.g., at least dozens) are involved in. This may be, for example, an open-source project to which you contribute changes. We will not cover this approach in this workshop, as the details may be specific to the project you're working on. However, the principles from approach #2 hold here.<br>
