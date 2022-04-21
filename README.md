# Git Commands

A list of git commands that relate back to DevOps related tasks.

## Git Add

Used to stage all files that will be commited to the repo. This also starts the process of keeping track of additions and deletions to code.

### Examples

```
git add <file_name, file_name, ...>   | Stages specific files
```
```
git add . | Stages all files in repo
```

## Git Commit
Stores the information about changes that have been made from `git add`. 

### Examples

```
git commit -m "<Message about commit relating to changes that were made>" | Takes a snapshot of all staged files, -m allows for a message about commit
```
```
git commit -a -m "<Message about commit relating to changes that were made>" | The `-a` is equal to using `git add .`
```

## Git Push
In simple terms, it updates the corresponding `origin` (remote version of branch) branch and syncs changes that are all stored from all commits

<img src="https://wac-cdn.atlassian.com/dam/jcr:0d181327-3fb0-44ec-9ab4-d6dea0fd406f/01%20Git%20push%20discussion.svg?cdnVersion=309" width="40%" height="40%">

### Examples
```
git push  | updates all the `origin` branch based on all the `changes` `remote` (the branch saved on local computer)
```
```
git push -u origin [branchname] | Used for pushing a new branch from remote for the first time. This creates a compliment origin branch `origin\(branchname)`
```

## Git Pull

Does a `git fetch` and `git merge` at the same time. In simple terms, it downloads the changes made on the remote repo and immediatly merges those changes with the local repo

<img src="https://wac-cdn.atlassian.com/dam/jcr:63e58c34-b273-4e48-a6b1-6e3ba4d4a0ea/01%20bubble%20diagram-01.svg?cdnVersion=309" width="40%" height="40%">
<img src="https://wac-cdn.atlassian.com/dam/jcr:0269bb2d-eb7f-43d8-80a2-8afa88d11eea/02%20bubble%20diagram-02.svg?cdnVersion=309" width="40%" height="40%">


### Examples

```
git pull  | A regular pull request
```

```
git pull --rebase | Similar to `git pull` but will stack the changes and not create a whole new node. It's good for if you want a clean history and want to make it look like the changes were stacked. (See image)
```

<img src="https://wac-cdn.atlassian.com/dam/jcr:d5633068-d448-4140-953e-2ab31553ce10/03%20bubble%20diagram-03-updated@2x%20kopiera.png?cdnVersion=309" width="40%" height="40%">

## Authors

* **Blake Cromar** - *Initial work* 

## Acknowledgments

* Adapted from Udacity, Machine Learning DevOps Engineer Nanodegree Program, 2022
* Atlassian.com for image on Git Push, https://www.atlassian.com/git/tutorials/syncing/git-push, 2022
* Atlassian.com for images on Git Pull, https://www.atlassian.com/git/tutorials/syncing/git-push, 2022
