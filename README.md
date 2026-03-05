# Git and GitHub Setup & Practice Lab

This repository documents the steps and commands used to set up Git on Windows, configure SSH keys, and practice basic and advanced Git workflows via the command line.

## 1. Installing Git on Windows
Installed Git using Winget (Windows Package Manager):
```cmd
winget install --id Git.Git -e --source winget

## 2. Global Git Configuration
Configured user details and the default branch name for all local repositories:
```cmd
git config --global user.name "omar"
git config --global user.email "omarsulaeman75@gmail.com"
git config --global init.defaultBranch main

## 3. SSH Key Generation
Created a secure ED25519 SSH key for GitHub authentication:
```cmd
ssh-keygen -t ed25519 -C "omarsulaeman75@gmail.com"

Copied the public key to add to GitHub's SSH Settings:
```cmd
notepad C:\Users\omars/.ssh/id_ed25519.pub

## 4. Initializing the Local Repository
Created the project folder and initialized Git:
```cmd
mkdir html_repo
cd html_repo
git init

## 5. First Commit and Linking to GitHub
Created a basic index.html file, committed it, and pushed it to a newly created remote repository:
```cmd
notepad index.html
git add index.html
git commit -m "Add simple HTML homepage"
git remote add origin git@github.com:OmarAlaaEl-Din/html_repo.git
git push -u origin main

## 6. Practicing Commits and Hard Resets
Added multiple lines to the HTML file, made four individual commits, and then deleted the last two commits:

Making the Commits:
```cmd
notepad index.html
git add index.html
git commit -m "Add first update"

notepad index.html
git add index.html
git commit -m "Add second update"

notepad index.html
git add index.html
git commit -m "Add third update"

notepad index.html
git add index.html
git commit -m "Add fourth update"

Deleting the Last Two Commits:
Used a hard reset to permanently erase the last two commits and their file changes:
```cmd
git reset --hard HEAD~2

## 7. Making a New Commit
Updated the file and committed the new state:
```cmd
git add index.html
git commit -m "commit after deletion"

## 8. Amending a Commit
Appended final text to the file and used the --amend flag to combine the new change with the previous commit, updating the commit message simultaneously:
```cmd
notepad index.html
git add index.html
git commit --amend -m "finish"
