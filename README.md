# Github Code Submission Tutorial For STAT 31015

The goal of the tutorial is to provide the necessary minimum information for successful code submissions. You can either submit your code via Github web user interface or *commit* your changes. If you are familiar with working with git, feel free to skip this tutorial. 

For any problems and further assistance, please contact our TAs.

## Getting Started

We have created an organization called **STAT-31015-Winter-2021** for this class. To get access to the organizations you are in, click the upper right corner of the Github webpage and click "Your organizations",

<img src="https://www.dropbox.com/s/faol7l2wnpg6582/Capture1.PNG?raw=1" width="160"/>

Find our class **STAT-31015-Winter-2021**,

<img src="https://www.dropbox.com/s/k4fb6akfxfub2jz/Capture2.PNG?raw=1" width="600"/>

By clicking through the name, now you will be directed to the organization page,

<img src="https://www.dropbox.com/s/apnc3l3ogwmsvsv/Capture3.PNG?raw=1" width="400"/>

Here you will find a repository (repo) with your first name. All the homework code should be submitted into this repo. If you don't find any repositories or the name doens't match, please contact us. Here we provide two ways to submit your code. If you are not familiar with git, we recommend you to use the web user interface. But feel free to try out more git features!

## Through Github Webpage (Recommended)

Now you can click and enter your repo. I will use my repo as an example. Initially the repo will look like the following:

<img src="https://www.dropbox.com/s/q7vjkf48wl6zb2p/Capture4.PNG?raw=1" width="1000"/>

First please create a folder named "HW#" where "#" is the number of homework. Creating a folder through webpage is a little bit tricky. Please follow the instructions in [this page](https://stackoverflow.com/questions/12258399/how-do-i-create-a-folder-in-a-github-repository) to create an empty folder. For example, in my repo I have created a folder named "HW4" for homework 4. Enter this folder. To upload your code, simply click the "Add file" button and select "Upload files". Follow the instrutions to select your files and finally click "commit changes". Now you can check on our repo to make sure the files have been successfully uploaded.

<img src="https://www.dropbox.com/s/qxyvve9zoyqhbmx/Capture5.PNG?raw=1" width="1000"/>

That's all! Feel free to stop here. If you are interested in more about git, please continue.

## Through Git

*This tutorial was adapted from [these notes](https://github.com/caam37830/git-tutorial) by Richard Zhu (richardzhu@uchicago.edu).*

### What is git?
`git` is a version-control system. It lets you track the whole history of changes made to code stored within a **repo** (repository), and it's especially powerful when collaborating on the same codebase with many people. It is designed to enable the following:

* periodic saving of work (called *committing*)
* returning to old versions when a problem is introduced
* creation of experimental code *branches* with out disturbing the main or working code
* *merging* the concurrent work of independent developers
* *remote* backup and storage of work
* tracking a *log* of project history

A git repo is stored locally on your computer. To make it visible to others online, it needs to be mirrored to somewhere in the cloud - and that's where GitHub comes in. GitHub (and competitors like Bitbucket, Gitlab) allow you to host git repositories on their remote servers, and serves as a pretty frontend to interact with your repositories.

## Getting started with git

### Installing git

Per the initial assumption, we assume you are using Mac or Linux, where `git` usually comes installed. Test this out by opening a terminal and typing `git version`. If it spits out `git version 2.XX.X`, then you have it installed.

If it gives you an error message, then you should follow the [instructions here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) to install git.

**Required**: Check that `git version` gives you the desired result.

### Configuring git and GitHub

After installing git, you need to supply your name and email to identify with your changes:

```bash
git config --global user.name "Your name"
git config --global user.email your@email.com
```

To interface with remote repositories stored on GitHub, you will also need to make a GitHub account. If you don't already have a [GitHub](https://github.com/) account, make one.

**Required**: In order to pull and push to private repos on GitHub, you will need to provide some form of authentication. The ideal solution here is to use SSH keys. Follow the [instructions here](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to generate a new SSH key for your computer and add it to your GitHub account.

**Required**: Check that running `git clone https://github.com/caam37830/caam37830.github.io.git` copies a directory called `caam37830.github.io` into the directory you ran it in, and verify that you see output like the following:

```bash
Cloning into 'caam37830.github.io'...
remote: Enumerating objects: 121, done.
remote: Counting objects: 100% (121/121), done.
remote: Compressing objects: 100% (72/72), done.
remote: Total 121 (delta 62), reused 88 (delta 35), pack-reused 0
Receiving objects: 100% (121/121), 22.76 KiB | 7.59 MiB/s, done.
Resolving deltas: 100% (62/62), done.
```

### Using GitHub classroom to pull your assignments

Homeworks will be released in GitHub Classroom. Each assignment will have an URL inviting you to automatically create a private repo within the `caam37830` GitHub organization to store your work in. 

Create a repo for the assignment, and go to the main page. You should see something like this, with additional files that help you:

![](https://www.dropbox.com/s/hmpiogjfgr5yqsh/Screen%20Shot%202020-10-01%20at%2015.53.47.png?raw=1)

To copy over the assignment files, click the `Code` dropdown menu (boxed in red), and click Clone > SSH. You can click the clipboard button (boxed in red) to copy the repo's ssh URL to your clipboard:

![](https://www.dropbox.com/s/cw7waxd9fo8usi1/Screen%20Shot%202020-10-01%20at%2015.56.07.png?raw=1)

**Check**: `git clone git@github.com:caam37830/test-assignment-richardzhu.git` will copy over the entire contents of the repo to a directory called `test-assignment-richardzhu` in whichever directory you call it in. As an example, suppose I run `cd ~/caam37830` and run `git clone git@github.com:caam37830/test-assignment-richardzhu.git`. I should have the directory `~/caam37830/test-assignment-richardzhu` containing all the homework files.

### Tracking the changes and submitting your assignments

Each assignment will have a `README.md` file detailing what you need to do to complete the assignment. After you clone the repository, you can make and test your changes locally. After you've made changes to the files and are satisfied with your work, run `git status`. It should output a list of tracked files that you modified, but haven't yet been *committed*, like so:

```bash
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   file_that_i_changed.py

no changes added to commit (use "git add" and/or "git commit -a")
```

If you don't commit changes and push them to GitHub, we won't be able to see them. To ensure that Git tracks your changes, make sure to add the files to staging like so: `git add file_that_i_changed.py`, repeating this for each file. If you run `git status` after doing this, you should see:

```bash
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   file_that_i_changed.py
```

Staging is a step prior to committing. It allows you to iteratively add changes you think should go into a *commit*. Once you're satisfied with your changes, you can make a commit and add a descriptive message like so: `git commit -m "add tests to file_that_i_changed.py"`. This will show you the commit you just made, with statistics on how many lines of code you added/deleted and how many files you modified:

```bash
[master f9fd5ba] add tests
 1 file changed, 2 insertions(+)
```

If you run `git status` now, you should see

```bash
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
```

This means that the tree of work your local git is tracking is one node (commit) further ahead than the remote tree. In order to update the remote tree and submit your changes, simply run `git push`.

That's it!

*Optional*: When doing your assignments, try to make your commits as atomic as possible instead of making one big commit with all your changes. That is, if you complete all the problems within `file.py`, `git add` and `git commit -m "solved problems in file.py"`. Repeat this for each file's changes. Making your changes as atomic as possible and writing descriptive commit messages is good practice, because it means you have a very clean work tree. Any colleagues reading the history can easily revert changes you made, and it minimizes the chance of big conflicts with other people's work you have to resolve manually.

## Missing the forest for the trees

Git is a way to represent a codebase (and changes to it) as a directed acyclic graph (DAG). The simplest possible DAG is one where each node is connected only to the next one. Such a DAG corresponds to the base case where one individual is working on one set of files with no branching:

![](https://www.dropbox.com/s/m1373zfdm91aaj4/Screen%20Shot%202020-10-01%20at%2016.39.40.png?raw=1)

There are more complex commands that allow you to introduce branches, merge branches, and perform other graph manipulations. But that's for another day.

## Basic git cheatsheet

In summary, here are the commands you should be familiar with:

- Stage files for a new commit: `git add file1.py file2.py file3.py file4.txt file5.md` 
  - You can use `glob` syntax to add all files ending in `.py` ( `git add *.py` ) or even all the files in the current folder (`git add ./*`) but it's not recommended. There are often many files you don't want to add to git history. These include compiled Python files `*.pyc` as well as Jupyter notebook checkpoints `.ipynb_checkpoints`, among others.
- Remove files from staging: `git reset file1.py`
  - If you accidentally staged a file you don't want to commit, use this.
- Make a new commit with all currently staged changes `git commit -m "descriptive message"`
- Push local work tree to remote work tree on GitHub: `git push` or `git push origin master`
- Pull remote work tree and update your local work tree: `git pull` or `git pull origin master`
  - You will do this often if you're collaborating on a project, or are using a project that is being actively worked on.
- Copy a remote repository to your machine: `git clone <url>`
- See current status of your repo: `git status`
- See a log of work tree, with commits and people who made them: `git log`
  - `git log --stat` to show which files and line numbers changed

## Extra resources

* Git homepage: http://git-scm.com/
* Git documentation: http://git-scm.com/doc
* Git Book: http://git-scm.com/book/en/v2
