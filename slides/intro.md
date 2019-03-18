# Girlpower workshop 19. mars
Velkommen til studentworkshop for jenter innen IT. 💖



## What is Git? 🤔
- Git is a Version Control System (VSC) that keeps track of all the changes to your project files.
- Allows you and the team to work on the same codebase
- Git stores every record of every change and makes keeping track of progress easy.



## What is GitHub? 🤔
- GitHub is a remote storage for Git repositoies
- Provides a simple way for people to collaborate and contribute to development projects
- open source &rArr; GitHub


## What I use GitHub for ✔
- Learning by analysing popular code repositories 🔬
- Finding libraries and tools other people have made instead of reinventing the wheel. ⚒️
- Sharing code and project to others 🥰
- Building up a portfolio of own projects, staring others, and following interresting persons 🤓



## Let's Get Started 💩

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


## Checkout a repository

```bash
git clone /path/to/repository
```


## Workflow
Our local repository consists of trees maintained by git
- Working directory - The actual files <!-- .element: class="fragment" -->
- Index - A staging area <!-- .element: class="fragment" -->
- HEAD - Pointer to your last commit <!-- .element: class="fragment" -->


## `add & commit`

- Propose changes (add it to the Index) by
```bash
git add <filename>
git add *
```

- To actually commit these changes do:
```bash
git commit -m "An awesome feature"
```


## `add & commit`

![flow](slides/git_flow.png)  <!-- .element style="background: white" -->


## Pushing changes
- Your canges are now in the HEAD of you local working copy.
- To send those changes to a remote repository (GitHub):
```bash
git push origin master
```


## Branching
```bash
git checkout -b feature_x

git checkout master

git branch -d feature_x

git push origin <branch>
```


## `update & merge`
- Get latest changes and merge them into your working directory
```bash
git pull
```
- Merge a branch to your selected one
```bash
git merge <branch>
```
- Check the difference between two branches
```bash
git diff <source_branch> <target_branch>
```


## `fetch & rebase`
- Get latest updates from remote without changing the working directory
- Unharmful, can do it whenever you want
```bash
git fetch
```
- Stack your commits on top of the remote's commit, and updates your working directory
```bash
git rebase
```


## `merge vs rebase`
![rebase_merge](slides/rebase_merge.png)


## Tagging 🏷
```bash
git tag 1.0.0
```


## Log
- Commits of certain author
```bash
git log --author=bob
```
- Compressed log
```bash
git log --pretty=oneline
```
- ASCII art tree of all the branches, decorated with names of tags and branches
```bash
git log --graph --oneline --decorate --all
```
- See only what files have changed
```bash
git log --name-status
```


## Replace local changes
- Replaces the changes in your working tree with the last content in HEAD. Changes already added to the Index, as well as new files, will be kept
```bash
git checkout -- <filename>
```
- Drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it.
```bash
git fetch origin
git reset --hard origin/master
```



## Git - Tips & tricks 🧚
- Built-in git GUI
```bash
gitk
```
- Use colorful git output
```
git config --global color.ui true
```
- Show log on just one line per commit
```bash
git config --global format.pretty oneline
```
- Interactive adding
```bash
git add -i
```


# Git - Tips & trics 2
"**A Dog**" = git log --**a**ll --**d**ecorate --**o**neline --**g**raph
```bash
git config --global alias.adog "log --all --decorate --oneline --graph"
```

![git log](slides/git_log.jpg)



## Trunk Based Development
> A source-control branching model, where developers collaborate on code in a single branch called ‘trunk’ *master*, resist any pressure to create other long-lived development branches by employing documented techniques. They therefore avoid merge hell, do not break the build, and live happily ever after.

[trunkbaseddevelopment.com](https://trunkbaseddevelopment.com/)



## Visual Studio Code <!-- .element: style="color:white"-->
<!-- .slide: data-background="slides/vscode.png" style="color:white"-->
- Best IDE, supports everything
- Amazing git integration
- Plugins for everything



## JavaScript & NodeJS
- Used to be a dynamic run-time language that runs on the client side in a web browsert
- NodeJS makes it possible to run JavaScript on the server side

<img class="plain" src="slides/nodejs.png" height="200wv"/>



# What is a REST API? 💎
- REST stands for *Representational state transfer*
- A style of web architecture
- JSON, XML
```json
{
  "basics": {
    "name": "Kristoffer-Andre Kalliainen",
    "github": {
      "username": "181192",
      "url": "https://github.com/181192"
    }
  },
  "work": [
    {
      "company": "Stacc Insight",
      "position": "Developer",
      "startDate": "01-12-2018"
    }
  ]
}
```


# How does it work?
- **Client-server** - The client handles the front end the server handles the backend and can both be replaced independently of each other.
- **Stateless** - No client data is stored on the server between requests and session state is stored on the client.
- **Cacheable** - Clients can cache response (just like browsers caching static elements of a web page) to improve performance.


## RESTful API's
A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.

| **URL**          | **HTTP Verb** | **Action** |
| ---------------- | ------------- | ---------- |
| /photos/         | GET           | index      |
| /photos/new      | GET           | new*       |
| /photos          | POST          | create     |
| /photos/:id      | GET           | show       |
| /photos/:id/edit | GET           | edit*      |
| /photos/:id      | PATCH/PUT     | update     |
| /photos/:id      | DELETE        | destroy    |



## Heroku
- Heroku is a cloud platform that lets companies build, deliver, monitor and scale apps
- Great CLI tool that makes you productive

<img class="plain" src="slides/heroku.png" />


## Get started
Install [heroku CLI](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)

```bash
heroku login
```

<img class="plain" src="https://media.giphy.com/media/zaezT79s3Ng7C/giphy.gif" height="200px">

Maybe a good idea to check that everything is ok:
```bash
node --version
yarn --version
git --version
```


## Clone the repository
```bash
git clone something
```
<img class="plain" src="https://media.giphy.com/media/RrVzUOXldFe8M/giphy.gif" height="400px">


## Deploy the application
- Create application
```bash
heroku create <name>-dev
```
- Push code to heroku remote
```bash
git push heroku master
#if failes
git remote add heroku https://git.heroku.com/<name_of_the_app>.git
```
- Scale the application
```bash
heroku ps:scale web=1
```
- Open the application via handy shortcut
```bash
heroku open
```
- View logs
```bash
heroku logs --tail
```


# Create a pipeline
- Create the app if you haven't
```bash
heroku create <name>-dev
```
- Create the pipeline
```bash
heroku pipelines:create --app <name>-dev --stage development <name>
```
- Add staging
```bash
heroku pipelines:add --app <name>-staging --stage staging <name>
```
- Add production? (Your turn 🤯)
- Promote application from dev to staging
```bash
heroku pipelines:promote --app <name>-dev
```
- Promote from stagin to production? (Your turn 🤓)