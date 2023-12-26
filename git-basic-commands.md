# Git Basic Commands

Basics commands of git to get started.

## Setting up Git in a directory.

1. **init**. To initialise a directory for using git. Usually the first command for intialising git inside a folder.

```
$ git init
```

2. **clone**. To clone a remote repository to the selected directory. This will create a replica of branch on Github to your local directory.

```
$ git clone https://github.com/saxena-codes/git
```

## Pushing changes to remote server.

1. **status**. To check the status of files modified or added.

```
$ git status
```

2. **add**. To add the current modifications/ alterations.

```
$ git add .
```

> **Note**: "." in the end of command above is for including all the files that have been modified. This can be replaced with name of file/ files to be added in case not all files are to be included.

3. **commit**. To commit the changes on the local branch.

```
$ git commit -m "Your message for the commit."
```

5. **push**. To push the local changes to the remote branch (on Github).

```
$ git push
```

## Checking the changes in a file/ files.

1. To check the changes in a file.

```
$ git diff README.md
```

2. To check all the changes made.

```
$ git diff
```

## The End
