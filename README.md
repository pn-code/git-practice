# git-practice

## Learning Intermediate-Advanced Git through The Odin Project

### Resources
https://www.theodinproject.com/lessons/javascript-a-deeper-look-at-git

### Overview

#### Changing the Last Commit
* Use this to replace the commit with an entirely new one
* Only amend commits that have not been pushed yet

``` bash
git commit --amend
```

#### Changing Multiple Commits
* This is a command which allows us to interactively stop after each commit we’re trying to modify.

``` bash
git rebase -i HEAD~2
git commit --amend
git rebase --continue
```

#### Squashing Commits
* This is a handy way of keeping our Git history tidy

``` bash
git rebase -i --root
```

The code below shows an example of how to squash a commit.

``` 
pick e30ff48 Create first file
squash 92aa6f3 Create second file
pick 05e5413 Create third file and create fourth file
```

#### Splitting Up a Commit
* Change pick to edit for the commit we’re going to split.

``` bash
git reset HEAD^
git add test3.md && git commit -m 'Create third file'
git add test4.md && git commit -m 'Create fourth file'
```

#### Best Practices
1. Make sure rewriting history is safe to do and others know you’re doing it.
2. Use these commands only on branches that you’re working with by yourself.
3. Only use -f flag when you have a great reason to use it
4. Don't push after every single commit, changing published history should be avoided when possible
5. Never amend commits that are already pushed
6. Never rebase a repo others are working out of
7. Never reset commits that are already pushed