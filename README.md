# Git Commands

A list of git commands that relate back to DevOps related tasks.

## Commands

### Git Add

Used to stage all files that will be commited to the repo. This also starts the process of keeping track of additions and deletions to code.

#### Examples

```
git add <file_name, file_name, ...>   | Stages specific files
git add .                             | Stages all files in repo
```

### Git Commit
Stores the information about changes that have been made from `git add`. 

#### Examples

```
git commit -m "<Message about commit relating to changes that were made>" | Takes a snapshot of all staged files, -m allows for a message about commit
```

### Git Push
In simple terms, it updates the corresponding `origin` (the branch saved on server) branch and syncs changes that are all stored from all `commit`s



#### Examples
```
git push  | updates all the `origin` branch based on all the `changes` `remote` (the branch saved on local computer)

```

## Authors

* **Blake Cromar** - *Initial work* 

## Acknowledgments

* Adapted from Udacity, Machine Learning DevOps Engineer Nanodegree Program, 2022
