# Introduction

# Chapter 1 - Getting Started

Just some **very** basic configuration I always like to have it handy.

```
git config --global user.name "John Doe" <br/>
git config --global user.email johndoe@example.com <br/>
git config --list <br/>
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
To see changes which have not been staged yet: <br/> 
`git diff`

To see changes that have been already staged: <br/>
`git diff --staged`

---

## Working dir operations