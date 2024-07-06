<h1 align="center" ><img height="100px" src="https://git-scm.com/images/logos/downloads/Git-Logo-1788C.svg"></h1>

Let’s start with the basics. Git is a version control system that allows you to track changes to your files and collaborate with others. It is used to manage the history of your code and to merge changes from different branches.

# To check your git version

```
git --version
```

# Repository

A repository is a collection of files and directories that are stored together. A repository is like a folder on your computer, but it is more than just a folder. It can contain other files, folders, and even other repositories. You can think of a repository as a container that holds all your code.

<img src="https://docs.chaicode.com/_astro/repo.CQAut4Jw_1Cvwlz.svg">

# Git Status

There is a difference between a software on your system vs tracking a particular folder on your system. At any point you can run the following command to see the current state of your repository:

```
git status
```

# Config Settings

To change your username, email, and other settings. Whenever you checkpoint your changes, git will add some information about your such as your username and email to the commit. There is a git config file that stores all the settings that you have changed.

To setup your email and username in this config file. Create an account on github and then use the email and username that you have created.

```
git config --global user.email "your-email@example.com"

git config --global user.name "Your Name"
```

### To check config settings

```    
git config --list
```

# Creating a Repository

Creating a repository is a process of creating a new folder on your system and initializing it as a git repository.

```
git init
```

`git init` command will create a new folder on your system and initialize it as a git repository. This adds a hidden `.git` folder to your project.

# Commit

commit is a way to save your changes to your repository. You can think of a commit as a snapshot of your code at a particular point in time. When you commit your changes, you are telling git to save them in a permanent way. This way, you can always go back to that point in time and see what you changed.

Usual flow looks like this:

<img src="https://docs.chaicode.com/_astro/commit.CZ_pUUof_1Y9b3g.svg">

# Complete git flow

<img src="https://docs.chaicode.com/_astro/gitflow.CjDHzFoj_dc900.svg">

When you want to track a new folder, you first use `init` command to create a new repository. 

Then you can use `add` command to add the folder to the repository.

After that you can use `commit` command to save the changes.

Finally you can use `push` command to push the changes to github.

# Stage
Stage is a way to tell git to track a particular file or folder.

```
git init

git add <file> <file2>

git status
```

Here we are initializing the repository and adding a file to the repository. Then we can see that the file is now being tracked by git. Currently our files are in staging area, this means that we have not yet committed the changes but are ready to be committed.

# Commit

```
git commit -m "commit message"
    
git status
```

Here we are committing the changes to the repository.

The `-m` flag is used to add a message to the commit. This message is a short description of the changes that were made.

# Logs

```
git log
```

This command will show you the history of your repository. It will show you all the commits that were made to the repository. You can use the `--oneline` flag to show only the commit message.

# Change Default Code Editor

You can change the default code editor in your system to vscode. To do this, you can use the following command:

```
git config --global core.editor "code --wait"
```

# Git Ignore

Gitignore is a file that tells git which files and folders to ignore. It is a way to prevent git from tracking certain files or folders.

```
 node_modules

.env

.vscode
```

Now, when you run the `git status` command, it will not show the `node_modules` and `.vscode` folders as being tracked by git.

# Branches in git

Branches are a way to work on different versions of a project at the same time. They allow you to create a separate line of development that can be worked on independently of the main branch. This can be useful when you want to make changes to a project without affecting the main branch or when you want to work on a new feature or bug fix.

<img src="https://docs.chaicode.com/_astro/branches.yYu2erFZ_Z1NQDag.svg">

## HEAD in git

The HEAD is a pointer to the current branch that you are working on. It points to the latest commit in the current branch. When you create a new branch, it is automatically set as the HEAD of that branch.

## Creating a new branch

To create a new branch, you can use the following command:

```
git branch

git branch bug-fix

git switch bug-fix

git log

git switch master

git switch -c dark-mode

git checkout orange-mode
```

### Some points to note:

- `git branch` - This command lists all the branches in the current repository.

- `git branch bug-fix` - This command creates a new branch called `bug-fix`.

- `git switch bug-fix` - This command switches to the `bug-fix` branch.

- `git log` - This command shows the commit history for the current branch.

- `git switch master` - This command switches to the `master` branch.

- `git switch -c dark-mode` - This command creates a new branch called `dark-mode`. the `-c` flag is used to create a new branch.

- `git checkout orange-mode` - This command switches to the `orange-mode` branch.
 
## Merging Branches

### Fast-forward merge

This one is easy as branch that you are trying to merge is usually ahead and there are no conflicts.

When you are done working on a branch, you can merge it back into the main branch. This is done using the following command:

```
git checkout main

git merge bug-fix
```

### Some points to note:

- `git checkout main` - This command switches to the `main` branch.

- `git merge bug-fix` - This command merges the `bug-fix` branch into the `main` branch.

<img src="https://docs.chaicode.com/_astro/fast-merge.BnHH-KQa_ZuiFbN.svg">

This is a fast-forward merge. It means that the commits in the bug-fix branch are directly merged into the main branch. This can be useful when you want to merge a branch that has already been pushed to the remote repository.

### Not fast-forward merge

<img src="https://docs.chaicode.com/_astro/notfast-merge.C_ZAD9Zp_zJoWb.svg">

In this type of merge, the `master` branch also worked and have some commits that are not in the `bug-fix` branch. This is a not fast-forward merge.

```
git checkout main

git merge bug-fix
```

The command are same.

The difference is resolving the conflicts. In a fast-forward merge, there are no conflicts. But in a not fast-forward merge, there are conflicts, and there are no shortcuts to resolve them. You have to manually resolve the conflicts. Decide, what to keep and what to discard. VSCode has a built-in merge tool that can help you resolve the conflicts.

<img src="https://docs.chaicode.com/_astro/conflict.-47xpPL4_ucXBc.svg">

## Managing conflicts

There is no magic button to resolve conflicts. You have to manually resolve the conflicts. Decide, what to keep and what to discard. I personally use VSCode merge tool. Github also has a merge tool that can help you resolve the conflicts but most of the time I handle them in VSCode and it gives me all the options to resolve the conflicts.

Overall it sounds scary to beginners but it is not, it’s all about communication and understanding the code situation with your team members.

## Rename a branch
 
```
git branch -m <old-branch-name> <new-branch-name>
```

## Delete a branch

```
git branch -d <branch-name>
```

## Checkout a branch

Checkout a branch means that you are going to work on that branch.

```
git checkout <branch-name>
```

## List all branches

```
git branch
```

# Git diff

The ``git diff` is an informative command that shows the differences between two commits. It is used to compare the changes made in one commit with the changes made in another commit.

### How to read the diff

- a -> file A and b -> file B
- ---- indicates the file A
- +++ indicates the file B
- @@ indicates the line number

Here the file A and file B are the same file but different versions.

## Comparing Working Directory and Staging Area

```
git diff
```

This command shows the unstaged changes in your working directory compared to the staging area. This command alone will not show you the changes made in the file A and file B, you need to provide options to show the changes.

## Comparing Staging Area with Repository

```
git diff --staged
```

This command shows the changes between your last commit and the staging area (i.e., changes that are staged and ready to be committed).

## Comparing between branches

```
git diff <branch-name-one> <branch-name-two>
```

This command compares the difference between two branches.

### Another way to compare the difference between two branches is to use the following command:

```
git diff branch-name-one..branch-name-two
```

## Comparing Specific Commits:

```
git diff <commit-hash-one> <commit-hash-two>
```

# Git Stash

Stash is a way to save your changes in a temporary location. It is useful when you want to make changes to a file but don’t want to commit them yet. You can then come back to the file later and apply the changes.

> Conflicting changes will not allow you to switch branches without committing the changes. Another alternative is to use the git stash command to save your changes in a temporary location.

```
git stash
```

This command saves your changes in a temporary location. It is like a stack of changes that you can access later.

## Naming the stash

```
git stash save "work in progress on X feature"
```

## View the stash list

```
git stash list
```

## Apply the stash

```
git stash apply
```

## Apply the specific stash

```
git stash apply stash@{0}
```

Here `stash@{0}` is the name of the stash. You can use the `git stash list` command to get the name of the stash.

## Applying and dropping the stash

```
git stash pop
```

## Drop the stash

```
git stash drop
```

## Applying stash to a specific branch

```
git stash apply stash@{0} <branch-name>
```

## Clearing the stash

```
git stash clear
```

# Git Tags

Tags are a way to mark a specific point in your repository. They are useful when you want to remember a specific version of your code or when you want to refer to a specific commit. Tags are like sticky notes that you can attach to your commits.

## Creating a tag

```
git tag <tag-name>
```

This command creates a new tag with the specified name. The tag will be attached to the current commit.

## Create an annotated tag

```
git tag -a <tag-name> -m "Release 1.0"
```

This command creates an annotated tag with the specified name and message. The tag will be attached to the current commit.

## List all tags

```
git tag
```

This command lists all the tags in your repository.

## Tagging a specific commit

```
git tag <tag-name> <commit-hash>
```

## Push tags to remote repository

```
git push origin <tag-name>
```

## Delete a tag

```
git tag -d <tag-name>
```

## Delete tag on remote repository

```
git push origin :<tag-name>
```

# Rebase in git

Git rebase is a powerful Git feature used to change the base of a branch. It effectively allows you to move a branch to a new starting point, usually a different commit, by “replaying” the commits from the original base onto the new base. This can be useful for keeping a cleaner, linear project history.

Some people like to use rebase over the merge command because it allows you to keep the commit history cleaner and easier to understand. It also allows you to make changes to the code without affecting the original branch.

## Merge commits

A merge commit is a commit that combines two or more commits into one. It is created when you merge two or more branches into a single branch. The merge commit contains all the changes from the original branches, and it is used to keep the project history clean and easy to understand.

<img src="https://docs.chaicode.com/_astro/mergecommits.BCy2lAZM_GTUD5.svg">

## Rebase

<img src="https://docs.chaicode.com/_astro/rebasegit.KNdYPNsD_Z1XWOos.svg">

Rebase is a powerful tool in Git that allows you to move a branch to a new starting point. It effectively replays the commits from the original base onto the new base. This can be useful for keeping a cleaner, linear project history.

Suppose you have a feature branch called feature-branch that you want to rebase onto the main branch.

## Ensure you are on the branch you want to rebase:

```
git checkout feature-branch
    
git rebase main
```

This will replay the commits from feature-branch on top of the latest changes in main.

## Resolve any conflicts:

If there are any conflicts, you will need to resolve them manually. You can use the merge tool in VSCode to resolve the conflicts.

```
git add <resolved-files>
    
git rebase --continue
```

# Git reflog

Git reflog is a command that shows you the history of your commits. It allows you to see the changes that you have made to your repository over time. This can be useful for debugging and understanding the history of your project.

## View the reflog:

```
git reflog
```

This will show you the history of your commits. You can use the number at the end of each line to access the commit that you want to view.

## Find specific commit

```
git reflog <commit-hash>
```

## Recover lost commits or changes

If you accidentally deleted a branch or made changes that are no longer visible in the commit history, you can often recover them using the reflog. First, find the reference to the commit where the branch or changes existed, and then reset your branch to that reference.

```
git reflog <commit-hash>
    
git reset --hard <commit-hash>
```

or you can use `HEAD@{n}` to reset to the nth commit before the one you want to reset to.

```
git reflog <commit-hash>
    
git reset --hard HEAD@{1}
```

---

<h1 align="center" ><img  height =150px src="github.svg"> </h1>


# What is Github?

Github is a web-based Git repository hosting service. It is a popular platform for developers to collaborate on projects and to share code. Github provides a user-friendly interface for managing and tracking changes to your code, as well as a platform for hosting and sharing your projects with others.

Github provides a variety of features and tools that make it easy to manage and track your code, including issues, pull requests, and code reviews.

### Some other alternative of Github are:

- Gitlab
- Bitbucket
- Azure Repos
- Gitea

# Configure your config file

If you havn’t done it already, you need to configure your git config file. You can do this by running the following command:

```
git config --global user.email "your-email@example.com"

git config --global user.name "Your Name"
```

This will set your email and name as your global settings. You can change these settings later by running the following command:

```
git config --global user.email "your-email@example.com"

git config --global user.name "Your Name"
```

Now you can check your config settings:

```
git config --list
```

This will show you all the settings that you have changed.

# Setup ssh key and add to github

You need to setup ssh key and add it to your github account. You can do this by following the instructions on the [Github website.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

You can find the exact steps on the website for both Windows and MacOS. The steps are same for both, only apple users need to add the ssh key to their keychain.

## Adding code to remote repository

Now that you have setup your ssh key and added it to your github account, you can start pushing your code to the remote repository.

Create a new Repo on your system first, add some code and commit it.

```
git init
    
git add <files>
    
git commit -m "commit message"
```

## Check remote url setting

You can check the remote url setting by running the following command:

```
git remote -v
```

This will show you the remote url of your repository.

## Add remote repository

You can add a remote repository by running the following command:

```
git remote add origin <remote-url>
```

> Here `<remote-url>` is the url of the remote repository that you want to add and origin is the name of the remote repository. This origin is used to refer to the remote repository in the future.

```
git remote add origin https://github.com/hiteshchoudhary/chai-something.git
```

## Push code to remote repository

```
git push remote-name branch-name
```

> Here `remote-name` is the name of the remote repository that you want to push to and `branch-name` is the name of the branch that you want to push.

```
git push origin main
```

## Setup an upstream remote

Setting up an upstream remote is useful when you want to keep your local repository up to date with the remote repository. It allows you to fetch and merge changes from the remote repository into your local repository.

To set up an upstream remote, you can use the following command:

```
git remote add upstream <remote-url>
```

or you can use shorthand:

```
git remote add -u <remote-url>
```

You can do this at the time of pushing your code to the remote repository.

```
git push -u origin main
```

This will set up an upstream remote and push your code to the remote repository.

This will allow you to run future commands like `git pull` and `git push` without specifying the remote name.

## Get code from remote repository

There are two ways to get code from a remote repository:

- fetch the code
- pull the code

`Fetch` the code means that you are going to download the code from the remote repository to your local repository. 

`Pull` the code means that you are going to download the code from the remote repository and merge it with your local repository.

## Fetch code

To fetch code from a remote repository, you can use the following command:

```
git fetch <remote-name>
```

Here `<remote-name>` is the name of the remote repository that you want to fetch from.

## Pull code

To pull code from a remote repository, you can use the following command:

> git pull `<remote-name>` `<branch-name>`

```
git pull origin main
```
Here `<remote-name>` is the name of the remote repository that you want to pull from and `<branch-name>` is the name of the branch that you want to pull.

---