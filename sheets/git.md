# Git

## Setup

### Git global setup

```bash
git config --global user.name "Prename Name"
git config --global user.email "email@example.com"
```

Just remove the `--global` flag for local setup.

### Create a new repository

```bash
git clone https://user@github.com/user/repo.git
cd repo
touch README.md
git add README.md
git commit -m "add README"
git push -u origin main
```

### Existing folder

```bash
cd existing_folder
git init
git remote add origin https://user@github.com/user/repo.git
git add .
git commit
git push -u origin main
```

### Existing Git repository

```bash
cd existing_repo
git remote add origin https://user@github.com/user/repo.git
git push -u origin --all
git push -u origin --tags
```

### Update remote location

```bash
git remote rm origin
git remote add origin <new-location>
git branch --set-upstream-to=origin/main main
```

### Stop tracking file

```bash
git update-index --assume-unchanged [path]
```

### Rename default branch of local clone

To update a local clone of a repository whose default branch name was changed (e.g. from `master` to `main`):

```bash
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a
```

## Remove password prompt

Caution: this will store the password unencrypted on the disk! Only use if it's safe on your machine!

```bash
git config credential.helper store
```

## Sign/verify commits

Use `git commit -S` by default for all commits

```bash
git config --global commit.gpgsign true
```

Set default key

```bash
git config --global user.signingkey <key-id>
```

In case GPG failed to sign data

```bash
export GPG_TTY=$(tty)
```

## Tags

### Add tag to specific commit

```bash
git tag -a v[version] [hash] -m "your tag description"
```

### Show commits since last tag

```bash
git log $(git describe --tags --abbrev=0)..HEAD --oneline
```

## Branches

### Remove Branches

```bash
git branch -d local-branch-name
git remote prune origin
```

## Submodules

Pull all submodules of the current repository (as they will not automatically retrieved by a `git clone`)

```bash
git submodule update --init --recursive
```
