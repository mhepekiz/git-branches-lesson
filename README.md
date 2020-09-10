# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) SOFTWARE ENGINEER IMMERSIVE

# Git Branches

## Objectives

- Create new branches on your own repo

- Make pull requests and merge on your repo
- <b>End Goal:</b> more comfortable using branches

## About Git

Git is a version control and repos can be thought of as storage of files and the history of the changes made to those files.

You own your repos and the changes allowed to those files. You can allow others to make changes to your files
(code base) but that is for another lesson. Next week we will cover working on a repo as a team and resolving merge conflicts.

## Create a new repo

Go to github.com/your-username?tab=repositories and create a new repo using the [NEW] green button

repositoty name is : branch-lesson

Select : Public

Check : Add a README.md file

[Create repository] green button

You now have a new repo to work with for this lesson

In github select the code button to copy the github address

    Confirm with a 😁: you have your repo created and ready to move on into VS

## Clone the repo in VS and make some changes

In VS terminal type `git clone <paste github address>`

Copy this text into your README.md

`this is MY REPO`

You now have a new repo with a README.md file and next we'll make a html file to start with

`touch index.html` will create a file on your master branch

Copy the following code into the index.html file

```
<html>
<head>
<title>This is my repo!</title>
</head>
</head>
<body>
Working on the master branch is no bueno!
</body>
</html>
```

TEST: In VS terminal run the `open index.html` to see your set up and confirm you have created the html file correctly

`git add .`

`git commit -m 'set up'`

`git push`

Refresh github to see your changes

    Confirm with a 🌶️: the alert and html page show up in your master branch on github

## Make a branch

Next we will make a branch! We need to make a branch so that the master branch remains untouched until we are ready to merge our new changes after testing and confirming the changes are functional. Developers use branches to protect the master branch from bugs and incomplete code.

the command to make a branch is:

`git checkout -b initials-branch-name`

### Notes on the command to create a branch:

_checkout_ is the command used to switch to branch name following the command

_-b_ is shorthand to create a new branch

_initials-branch-name_ is the name of the newly created branch. You want to use your initals and a one to two word description of what you are doing on this branch. **Use your initials and a description for all of your branches!** example for this lesson: `tf-js`

There a command to create a branch without switching to that branch `git branch <initials-branch-name>` but `git checkout -b <initials-branch-name>` is the perferred way and you should use that one for the remainder of the lesson

Your zsh will now say the name of your branch, not master

    Confirm with a 🌳: the name of the branch changed

## Make changes on your branch

`touch script.js`

Paste this code in your newly created script.js file

`alert("Hello! I am an alert box!!");`

Edit the index.html body text and to add the script tag within the body tag

```
<html>
<head>
<title>This is my repo!</title>
</head>
</head>
<body>
Instead of working on the master branch this is my newly created branch, woohooo!
<script type="text/javascript" src="script.js"></script>
</body>
</html>
```

Run the command: `open index.html`

    Confirm with a 🎯: the alert and text changed in the html page in the browser

Run the command: `git status`

you should see

```javascript
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        script.js

```

`git add .`

`git commit -m 'add index and js'`

`git push` will not work!!

    ➜  branch-lesson git:(tf-js) git push
    fatal: The current branch tf-js has no upstream branch.
    To push the current branch and set the remote as upstream, use

    git push --set-upstream origin tf-js

YOU NEED TO PUSH TO YOUR BRANCH!

`git push origin tf-js`

Go to github and confirm your branch was successful by checking the branches dropdown

    Confirm with a 🦄: the push was successful

## MERGING FROM GITHUB WEBSITE

If you have successfully pushed your branch, there will be a button to select [Compare & pull request]

Scroll to see your edits to the index.html and script.js. If everything looks good, we're ready to merge

Select the [Create pull request] button. Here the commit message will be the title, which you may want to change and/or add a description.

Select the [Merge pull request] button

Select the [Confirm merge] button

Select the [Delete branch] button. Since you merged these changes into your master, its best to remove it. Don't forget that it still lives on your machine.

Going back to your code in github you will now see your changes merged into your master branch

BUT WAIT YOU ARE NOT DONE!

In your VS terminal run the command ` git checkout master` this will switch your branch to master on your machine

Now you need to run the command ` git pull` this will pull down the merged changes that now live on the master branch

COOL! We have successfully created a branch and merged it into the master branch

Notes:

- Git status is your new best friend
- Zsh terminal is used to see what branch you are on

<br>
    
    Confirm with a 🌈: master has your branches changes

<br>
<br>

## Let's get some muscle memory 💪 and make a "another-change" branch

Run the command ` git checkout -b initials-another-change`

In index.html change the body text to: `I love making branches!`

Let's examine the git tab in the VS code editor. Using this tab BEFORE you add is the recommendation. It will allow you to make changes if needed before you add and commit your files. When everything looks as you expect it to, we're almost ready to add and commit.

### ❓ What should you do before adding and commiting?

<br>

<details>
  <summary>Answer:

 </summary>
 <br>

Get in the habit of running to run this command first `git status` everytime before you add and commit.

    Changes not staged for commit:
        (use "git add <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
                modified:   index.html

    no changes added to commit (use "git add" and/or "git commit -a")

</details>

<br>

`git add .`

`git commit -m 'edit index'`

`git push origin another-change`

    Confirm with a 💪: the another-change branch is pushed up to github

## MERGING FROM VS TERMINAL

Instead of using the github interface to merge we will use the terminal

NOTE: Although this is an option, it is recommended that you use the github site for your group project. The interface on github gives you more information if a git merge conflict happens, _which probably will happen at least once during project 3._ We will cover more on that in the next lesson.

Steps to merge from VS terminal:

`git checkout master`

`git merge another-change`

`open index.html`

BUT WAIT YOUR NOT DONE!

### ❓ What do you think you need to do to finish this merge?

<br>

<details>
  <summary>Answer:

 </summary>
 <br>

`git push`

IMPORTANT: your files were merged on your computer and need to live on github for your team to be able to see and use your changes. So don't forget to push!

</details>

<br>

    Confirm with a 🏋️: master has all of the changes

## Branch cleanup

Remember when we merged the first branch using github and selected the delete button when the merge was complete? The branch still lives on your machine. Once the branch is no longer being used, its good practice to delete it from your machine.

Run the command: `git branch` this will show you what branches are on your machine, not on github. If you want to view or delete the branches on github you will need to do that from the browser interface.

Run the command: `git branch -D <initials-branch-name>`

Clean up your branches

NOTE: You will not be able to delete the branch you are currently on

### IMPORTANT: Always make a branch off of the master branch!

If this all of this seems like a lot, it's because it is! But it will become more intuitive the more you do it so please get some reps in over the weekend 💪💪💪

It might be helpful for you to make your own notes/cheatsheet with the necessary steps to merge, to be used while in project week.

### Additional Resources

[3.2 Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
