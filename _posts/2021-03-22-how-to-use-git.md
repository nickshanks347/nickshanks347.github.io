---
title: Git started with GitHub 
published: true
---

### So why Git? 
It's a distributed source control system. Most people use it with a central server to serve as a central repository for collaborations. It can be massively scaled. It's free and open source. It was developed for Linux project requirements. Most operations in git are local, there are only a few commands that require a network connection. Since most operations are local, git is extremely fast. Git is the most popular version control system. 
* * *
### Key concepts
Repositories contains files, history and configurations managed by Git. 
Three (four) states of Git:
1. Working directory - folder which holds project files. Files may or may not be managed by Git. Hidden folder called .git which contains the actual Git repository. The Git repository manages the Git commit history - that is all the changes that are finalized and permanently part of the Git repository.
2. Staging area - pre-commit holding area - referred to as the Git index. Files can be moved in and out of the staging area without impacting the Git repository.
3. Commit - Git repository (history) - changes which are part of the repository
4. Remote repository (GitHub) - last step in basic Git workflow
* * *
### Now the theory
The last concept is the master branch. A branch is a timeline which contains your changes (commits). Git provides a default branch called master.

We need to configure the name and email address for Git. Type:
`git config --global user.name "Your Name"`
`git config --global user.email "yourname@domain.com"`
You can confirm the values with `git config --global --list`

To get a remote repository to your local system, use `git clone <url>`

Use `git status` to get the state of the repository. The default branch is `master` by convention. `origin/master` is the master branch on the remote repository. Git also says `working directory clean`, which means there are no changes between the working directory, staging area and remote repository. 

Untracked files are files in the working directory that haven't been added to Git yet. Use `git add <filename>`. Now do a `git status` and you'll see 'new file: <filename>' which Git describes as changes to be committed. Use ` git commit -m "<commit message>" ` to commit to the local repository. If you do a ` git status `, it'll show 'working directory clean' as there are no pending changes.

To push changes to the remote repository (from local) type `git push origin master`. This version of the git push command sets which remote repository to push to, and which branch to push. 

To start a repository locally without any source code remotely. To create a fresh new repository, head into the root folder that will contain the repository directory and type `git init <reponame>`, Git will create a new folder and initialize a fresh repository inside it. If you use `git status`, it should say that you're on the master branch. Create a new file in the folder with nano, or notepad, etc. Now `git status` says that we have an untracked file. Use `git add <filename>` and then type `git status` and it'll say `new file: <filename>`. If you use `git commit` without any extra parameters, it'll open the default editor with a default commit message; add your commit message at the top of this file, this allows multiple-line commit messages. On `git status`, "(root-commit)" is the very first commit. 

You can do a `git init` and it'll use the current folder as the working directory. To add all files at once to the Git staging area, use `git add .`, then do a `git status` and it'll show that all files have been recursively added. Do `git commit -m "<commit message>"` to finally commit the changes.
