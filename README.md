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

## Git Merge

Often used to add changes from one branch to another. The command assumes you are currently on the branch that has changes and you mention the branch you want to merge on to.

<img src="https://wac-cdn.atlassian.com/dam/jcr:7afd8460-b7bf-4c42-b997-4f5cf24f21e8/01%20Branch-2%20kopiera.png?cdnVersion=309" width="40%" height="40%">
<img src="https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=309" width="40%" height="40%">

### Examples


```
git merge <branch name you are merging with> | merges changes from one branch to another branch, fast forwarding will be done if possible
```
*"fast forwarding is when there is a linear relationship betwen the two branches (no splitting) and the banch that is being merged on to is simply moving forward in commit history."*

```
git merge <branch name you are merging with> --no-ff -m "<messege about merge>"| forces a merge to have a new commit object (no fastforwarding) which can be good for perserving git history
```

<img src="https://nvie.com/img/merge-without-ff@2x.png" width="40%" height="40%">

## Git Branch

Usually paired with another command, but it's primary purpose is to handle various elements of branching one's code.

### Examples

```
git branch | Allows you to view all branches
```

```
git branch <branch name> | Creates a new branch 
```

```
git branch -d <branch name>| Allows you to delete a branch 
```

## Git Checkout

Primarly used to switch between branches. Normally, when you switch to a branch you start at the commit that is labled as HEAD. If you have a specific commit ID you can switch to a branch at that point. You can also modify and merge from a point that is a commit that isn't considered HEAD. You can find commit IDs with `git log`.

### Examples

```
git checkout <branch name you want to switch to> | Adds a new branch based on current head
```

```
git checkout -b <new branch name> | Creates a new branch while also switching to it
```

```
git checkout <commit id> | This allows you to be on a branch at a specific commit
```

## Git Status

Used to provide information about changes that are different than HEAD

### Examples

```
git status | gives a report about changes that differ from HEAD
```

## Git Stash

Allows you to stash all staged and unstaged changes. This is great if you want to switch branches as you can't have changes before one switches.

### Examples 

```
git stash | stores changes that have been make and restores code back to before the changes were made
```

```
git stash pop | Reverts the code back to before a `git stash` was called
```

## Git Log

Show a record of a list of commits in history. Press `return` to retrieve more history. Press `q` to exit log.

### Examples

```
git log | shows a list of commits
```

## Git Clone (SSH key method)
Used to clone a remote repo onto one's local computer.

### Steps

1. Check to see if you have a public key already. In your terminal type `~/.ssh` as this is where they are stored by default.
2. If you already have ssh keys you will see files called `id_rsa` and `id_rsa.pub`. If you do have these files skip to step 6.
3. If you don't already have the key type `ssh-keygen -o` in your terminal. This will create the key you need.
4. Press `return` when it asks where you would like to save them. If you do this it will save those keys in the default location.
5. Press enter twice when its asks for a passphrase and asks again for confirmation.
6. Now that you have a puplic key type (or already have one) type 'cat ~/.ssh/id_rsa.pub'. This will print out the key. Copy that including the `ssh-rsa` part of the code.
7. Go to your github profile, go to the top right and click on the arrow next to your profile image.
8. Click settings.
9. On the left hand side look for "SSH and GPG Keys" and click on it.
10. Click on the green button that says "New SSH Key".
11. Give the key a title. I recommend something that indicate which computer key came from. After you do that, paste the SSH key in the text box where it is titled "Key". If you want to add more SSH keys so more computers can access your repo then you can repeat steps 6-11 once you have a computer's public key.
12. Now that github knows that there is a computer with a SSH key, that is given permission to clone, navigate to repo go to the repo you want to clone.
13. There is a green button that says "Code". Click on it.
14. Click on the tab that says "SSH".
15. There's a small button that looks like two squares. Click on it and it will copy everything in the box to the left of it to your computer's clip board.
16. Open your terminal if it's not already open.
17. Navigate to the folder you want this repo to be in.
18. Type `git clone <text that was copied to your clipboard in step 15>`.
19. Your now have that repo cloned to your local machine.

## Git Reset

Used to reset a branch to a commit.

### Examples
```
git reset --hard HEAD~<number of commits from head> | HEAD is the latest commit. This will reset the current branch `X` number of commits from HEAD and leave it uncommited. 
```

## Authors

* **Blake Cromar** - *Initial work* 

## Acknowledgments

* Adapted from Udacity, Machine Learning DevOps Engineer Nanodegree Program, 2022
* Atlassian.com for image on Git Push, https://www.atlassian.com/git/tutorials/syncing/git-push, 2022
* Atlassian.com for images on Git Pull, https://www.atlassian.com/git/tutorials/syncing/git-push, 2022
* Atlassian.com for image on Git Merge, https://www.atlassian.com/git/tutorials/using-branches/git-merge, 2022
* nvie.com, article by Vincent Driessen, for image on git Merge, https://nvie.com/posts/a-successful-git-branching-model/, 2010
* git-scm.com, steps on how to create a SSH key, https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key, 2022
