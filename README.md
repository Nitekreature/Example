# C++ Example Repo

Example repository with step-by-step instructions for setting up a git repo locally.

## Getting Started

### Installing Git

**If you are using Visual Studio Community Edition, you can skip this step.**
> git is built into the program and can be accessed via the `Developer Powershell` (`Tools > Command Line > Developer Powershell`).

Otherwise, you will most likely need to [download and install git](https://git-scm.com/downloads). Download for your operating system and follow the instructions the installer gives you.

Now, you should have git accessible from some terminal in your computer, either in Visual Studio or otherwise.

### Forking and Cloning the Repo

Navigate to the [Example repo (this page)](https://github.com/tro2/Example), in the top-right corner hit `Fork`. You can leave the settings as default, just make sure you are okay with the name and description.

Once completed, you should be at your own repository. On the right-hand side, there is a button labeled `Code`, in this popup there is an HTTPS link for cloning your repository, copy it!

Now, go back to your terminal and type `git clone` and paste the copied url. It should look like `git clone https://github.com/tro2/Example.git`.

The repo should now be accessible in the `/Example` folder.

### Fetching and Pulling

`git fetch` is an important command for making sure your repo is up to date with the remote. Always run it before committing changes, as you do not want to have to resolve conflicts that may arise otherwise.

### Repo Status

A very helpful command for checking the state of your repo is the `git status` command. This shows information about new/modified files, branches, whether your local repo is behind/ahead the remote, and more.
It can be checked by running `git status`. This is an example output of the status command as I'm updating this README file:
```git
C:\Workspace\Projects\Example>git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
A key line to note is `Your branch is up to date with 'origin/main'. This means you are up to date with the remote branch

### Pulling

Now that your local repository is set up, before making any changes you __always__ want to make sure it's up to date with the remote. To do this, execute the following commands:
```git
git fetch
git pull
```

### Pushing

## Acknowledgments

  - Atlassian git
  - Github
  - Professor Ahmed Alweheiby
