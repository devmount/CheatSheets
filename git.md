# Git

## Git global setup

    git config --global user.name "Prename Name"
    git config --global user.email "email@example.com"

## Create a new repository

    git clone https://user@github.com/user/repo.git
    cd repo
    touch README.md
    git add README.md
    git commit -m "add README"
    git push -u origin master

## Existing folder

    cd existing_folder
    git init
    git remote add origin https://user@github.com/user/repo.git
    git add .
    git commit
    git push -u origin master

## Existing Git repository

    cd existing_repo
    git remote add origin https://user@github.com/user/repo.git
    git push -u origin --all
    git push -u origin --tags