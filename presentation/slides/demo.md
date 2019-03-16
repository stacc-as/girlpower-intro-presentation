# What is Git?
- Git is a Version Control System (VSC) that keeps track of all the changes to your project files.
- Allows you and the team to work on the same codebase
- Git stores every record of every change and makes keeping track of progress easy.



# What is GitHub?
- GitHub is a remote storage for Git repositoies
- Provides a simple way for people to collaborate and contribute to development projects
- open source &rArr; GitHub


# What I use GitHub for
- Learning by analysing popular code repositories
- Finding libraries and tools other people have made instead of reinventing the wheel.
- Sharing code and project to others
- Building up a portfolio of own projects, staring others, and following interresting persons



# Let's Get Started

- Setting your commit username and email address <!-- .element: class="fragment" -->
```bash
git config --global user.name "181192"
git config --global user.email "181192@stud.hvl.no"
```
<!-- .element: class="fragment" -->

- Verify the settings <!-- .element: class="fragment" -->
```bash
git config --global user.name
git config --global user.email
```
<!-- .element: class="fragment" -->


# Checkout a repository

```bash
git clone /path/to/repository
```


# Workflow
Our local repository consists of trees maintained by git
- Working directory - The actual files <!-- .element: class="fragment" -->
- Index - A staging area <!-- .element: class="fragment" -->
- HEAD - Pointer to your last commit <!-- .element: class="fragment" -->


# `add & commit`

Propose changes (add it to the Index) by
```bash
git add <filename>
git add *
```

To actually commit these changes do:
```bash
git commit -m "An awesome feature"
```


# `add & commit`

![add_commit](slides/add_commit.png)  <!-- .element style="background: white" -->


# Pushing changes
Your canges are now in the HEAD of you local working copy. To send those changes to a remote repository (GitHub):
```bash
git push origin master
```


# Branching
```bash
git checkout -b feature_x

git checkout master

git branch -d feature_x

git push origin <branch>
```


# `update & merge`
```bash
git pull

git merge <branch>

git add <filename>

git diff <source_branch> <target_branch>
```


# Tagging
```bash
git tag 1.0.0
```


# Log
```bash
# Commits of certain author
git log --author=bob

# Compressed log
git log --pretty=oneline

# ASCII art tree of all the branches,
# decorated with names of tags and branches
git log --graph --oneline --decorate --all

# See only what files have changed
git log --name-status
```


# Replace local changes
```bash
# replaces the changes in your working tree with the last content in HEAD. Changes already added to the Index, as well as new files, will be kept
git checkout -- <filename>

# Drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it.
git fetch origin
git reset --hard origin/master
```


# Git - Tips & tricks
- built-in git GUI
```bash
gitk
```
- use colorful git output
```
git config --global color.ui true
```
- show log on just one line per commit
```bash
git config --global format.pretty oneline
```
- Interactive adding
```bash
git add -i
```



# Visual Studio Code
- Best IDE, supports everything
- Amazing git integration
- Plugins for everything