# Git

## Setup

### Git global setup

    git config --global user.name "Prename Name"
    git config --global user.email "email@example.com"

Just remove the `--global` flag for local setup.

### Create a new repository

    git clone https://user@github.com/user/repo.git
    cd repo
    touch README.md
    git add README.md
    git commit -m "add README"
    git push -u origin master

### Existing folder

    cd existing_folder
    git init
    git remote add origin https://user@github.com/user/repo.git
    git add .
    git commit
    git push -u origin master

### Existing Git repository

    cd existing_repo
    git remote add origin https://user@github.com/user/repo.git
    git push -u origin --all
    git push -u origin --tags

## Remove password prompt

Caution: this will store the password unencrypted on the disk! Only use if it's safe on your machine!

    git config credential.helper store

## Sign/verify commits

Use `git commit -S` by default for all commits

    git config --global commit.gpgsign true

Set default key

    git config --global user.signingkey <key-id>

## Tags

### Add tag to specific commit

    git tag -a v[version] [hash] -m "your tag description"
