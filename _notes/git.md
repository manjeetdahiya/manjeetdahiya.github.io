---
layout: post
title: Git Cheat Sheet
---

### Create a new repository
```git init <directory>```

```git init --bare <directory>```

Bare flag creates a repository without a working directory in it. Used for creating a repository on a server.

### Clone existing repository
```git clone <repo> [<directory>]```

### List all branches
```git branch```

### Create a branch; does not switch to it though
```git branch <name>```

### Delete a branch
```git branch -d <name>```

### Force delete a branch
```git branch -D <name>```

### Push a local branch to remote

```git push <remote> <branch-name>```

### Following command sets the upstream too: 
Assigns the association b/w a local and a remote branch and 
doesn't ask which branch to push/pull to in future.

```git push -u <remote> <branch-name>```

e.g.

```git push origin name```


### Delete a remote branch:
```git push origin --delete <branch-name>```

### Rename the current local branch
```git branch -m <name>```

### Switch branch
```git checkout <branch>```

Following command is needed if a file/dir exists with the same name as branch:

```git checkout <branch> --```

### Create and switch branch
```git checkout -b <branch>```

If you have local changes in your working dir, these will come as local changes in the new branch created.
This command is equivalent to following two commands:

```git branch <name>```

```git checkout <name>```

### Merge the branch 'branch-name' into the current branch
```git merge <branch-name>```

### Push a branch only
```git push -u origin <branch-name>```

### Set/unset an external diff tool
```git config --global diff.external /path/to/diff/tool```

```git config --global --unset diff.external```

### Set vim as the default editor
```git config --global core.editor "vim"```

### Set git email
```git config --global user.email "xyz@xyz.com"```

### Update the last commit message
```git commit --amend```

### List remotes
```git remote -v```

### Add remote
```git remote add origin sri.cse.iitd.ernet.in:repo/notes```

### Reset local staged changes
```git reset```


### Submodule status
```git submodule status```