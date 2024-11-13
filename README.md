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

### Repo Status

A very helpful command for checking the state of your repo is the `git status` command. This shows information about new/modified files, branches, whether your local repo is behind/ahead the remote, and more.
It can be checked by running `git status`. This is an example output of the status command as I'm updating this README file:
```diff
C:\Workspace\Projects\Example>git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
A key line to note is `Your branch is up to date with 'origin/main'`. This means you are up to date with the remote branch, which you can check by running the `fetch` command in the next section.

### Fetching and Pulling

`git fetch` is an important command for making sure your repo is up to date with the remote. Always run it before making changes, as you do not want to have to resolve conflicts that may arise otherwise. Always check ` git status` after fetching to see the status of the repo:
```git
C:\Workspace\Projects\Example>git fetch

C:\Workspace\Projects\Example>git status
On branch main
Your branch is behind 'origin/main' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```
Here, my local branch is behind my remote, and needs to be brought up to date before I make any more changes. This can be done with `git pull`.
```git
C:\Workspace\Projects\Example>git pull
Updating 416b2f7..04fc882
Fast-forward
 README.md | 48 ++++++++++++++++++++++++++++++++++++++++++------
 1 file changed, 42 insertions(+), 6 deletions(-)
```

To summarize, always `fetch`, check `status`, and `pull` before making changes.

### Pushing

Now, assuming your local repo is all up to date, you can make changes to the repo. This can be adding a file, modifying a file, or deleting one. For this example, I've made some changes to the README.

As always, I'm going to check the state of the repo with `git status`
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

I have a modified file, which I can ready for commiting by staging it with `git add README.md`. The `add` command allows you control over what changes you commit, which is helpful for more complicated projects.
```git
C:\Workspace\Projects\Example>git add README.md

C:\Workspace\Projects\Example>git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
```

Now that your changes are staged, you can make a commit by running `git commit -m "Enter message here"`. Replace the message text with something descriptive about the commit, usually just an explanation of what the changes are.
```git
C:\Workspace\Projects\Example>git commit -m "Updated README"
[main 6942ae4] Updated README
 1 file changed, 68 insertions(+), 9 deletions(-)
 ```

We're ready for the last step, to make your changes permanent on the remote repo. To do this, run `git push`
```git
C:\Workspace\Projects\Example>git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 2.33 KiB | 2.33 MiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/tro2/Example.git
   04fc882..6942ae4  main -> main
```

### Summary

To conclude, there are 8 functions you need to know for daily git use:
`Fork` - creates your own copy of a repo that you are free to modify
`git clone` - makes a local copy of a remote repo
`git status` - shows the state of your local repo
`git fetch` - updates information about the remote repo
`git pull` - grabs and merges remote changes into your local repo
`git add` - stages files for commit
`git commit` - commits staged changes
`git push` - pushes local changes to the remote repo.

Now this list, is not exhaustive by any means, we haven't covered branches, PRs, initializing repositories, multiple remotes, and a host of other topics. If you would like to learn more, there is a wonderful set of tutorials and a comprehensive wiki found at [https://git-scm.com/doc](https://git-scm.com/doc)

The slides accompanying this presentation can be found [here](https://docs.google.com/presentation/d/1m79pmaxq_Kb8-SeMMtA7E4FZiHdPz4OXNoXgtvHSPG0/edit?usp=sharing)

## Acknowledgments

  - Atlassian git
  - Github
  - Professor Ahmed Alweheiby
