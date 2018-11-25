# Introduction

My personal cheat sheet for Git. This started as a way to keep notes after reading [Pro Git](https://git-scm.com/book/en/v2).

This is a work in porgress.

# Chapter 1 - Getting Started

Just some **very** basic configuration I always like to have it handy.

```bash
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
git config --list
git config --global core.editor emacs
```

# Chapter 2 - Git Basics

## Ignoring files

Git ignore files are written using **glob** patterns.

- ignore all .a files
   - *.a
- but do track lib.a, even though you're ignoring .a files above
   - !lib.a
- only ignore the TODO file in the current directory, not subdir/TODO
   - /TODO
- ignore all files in the build/ directory
   - build/
- ignore doc/notes.txt, but not doc/server/arch.txt
   - doc/*.txt
- ignore all .pdf files in the doc/ directory and any of its subdirectories
   - doc/**/*.pdf

---

## Diff
To see changes which have not been staged yet: `git diff` 

To see changes that have been already staged: `git diff --staged`

---

## Working dir operations

Removing a file from Git: `git rm <file>`. On the next commit the file will be gone. No need to do `git add` to stage the change.

If you want to stop tracking a file but keep the file (for example, installers or logs):
`git rm --cached <file>`

If you deleted a file manually, you'll need to stage the change. For example:
```bash
#1 You create a file
touch test.txt
#2 Add the file so it gets tracked
git add test.txt
#3 Commit your changes
git commit -m "Add file test.txt."
#4 Delete the file using bash 'rm' command and not 'git rm'
rm test.txt
#5 Run git status and check the file is being marked as deleted
#6 Add your change (file deletion) to be commited
git add test.txt
#7 Commit your changes
git commit -m "Remove test.txt file."
```

To rename a file, use `git mv <originalName> <newName>`.

---

## Git Log

`git log` will provide the full history in reverse chronological order.

|git log|Description|
|-|-|
|`-p -2`| Shows last 2 commits and patch information (`git diff` for each of them). `-p` or `-patch` are synonyms. `-#` is also valid for other log commands.|
|`--stat`|Additional stats per commit.|
|`--pretty=oneline`| Format the output in 1 line per commit.|
|`--pretty=format: <format>`| Check this link to see [all available formats](https://git-scm.com/docs/pretty-formats).|
|`--graph`|Shows a graph of how commits are mapped to branches.|

---
