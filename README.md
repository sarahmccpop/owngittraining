# owngittraining

## Exercise 1
https://github.com/nnja/advanced-git/blob/master/exercises/Exercise1-SimpleCommit.md

`cd owngittraining`

`echo "console.log('Hello world');" > gitexercises.js`

`git add gitexercises.js`

First commit with commit message in command line
`git commit -m "Initial commit"`

Viewing the .git tree
`tree .git`

Git is a key value store. The value is the data and the key is the hash of the data, which you can use to retrieve contents.

The Key is the SHA1 - a 40 digit hexadecimal number. Should always be the same if the given **input is the same.**

Explored the objects in the tree using - 

`git cat-file -t 0d0f` = tree 

`git cat-file -t 7bc4` = blob

`git cat-file -t b86d` = commit 

Looked at the contents of the blob by changing `-t` to `-p`

`git cat-file -p 7bc4` = `console.log('Hello world');`

Looked at HEAD variable.  HEAD is just git's pointer to "where you are now," usually referring to the current branch. HEAD is a pointer to the **current commit.** Head is usually a pointer to the current branch.
`cat .git/HEAD` = `ref: refs/heads/main`

Looked at master reference, which points to last commit. Code to do this in exercise was `cat .git/refs/heads/master` but `cat .git/refs/heads/main` worked for me. Main instead of master. I got this as HEAD pointed to main not master

Used `git log --oneline` to view the hash of the latest commit. This opened in a new tab and I used `q` to close it. 

I created a new branch called new_branch by using `git branch new_branch`. This creates a new branch but **does not switch to it.**

To look at the branches I used `tree .git/refs`. I could see my `main` branch and my `new_branch` branch under `heads`.

Nothing has been pushed yet.

## Exercise 2
https://github.com/nnja/advanced-git/blob/master/exercises/Exercise2-StagingAndStashing.md

I created a new branch by using `git branch exercise2` and switched to it by using `git checkout exercise2`

I used `git ls-files -s` to view. This lists all files that are in the staging area. The staging are what files are going to be part of the next commit. You should consider the baseline staging area as being an exact copy of the latest commit.

The files in your working area that are **also not** in the staging are not handled by git. These are called **untracked files**.



