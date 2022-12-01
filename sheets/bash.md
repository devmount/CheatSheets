# Bash

## Compression

Create a `.tar.gz` or `.zip` file

```bash
tar -czvf file.tar.gz directory-to-compress/
zip -r file.zip directory-to-compress/
```

Extract contents of a `.tar.gz` or `.zip` file

```bash
tar -zxvf file.tar.gz
unzip file.zip
```

## GPG

Import public key of someone

```bash
gpg --import some-one.key
```

See all imported public keys

```bash
gpg --list-keys
```

Encrypt a file

```bash
gpg --encrypt --armor -r some-one@server.com file.txt # or
gpg -e -u "Sender Name" -r "Receiver Name" file.txt
```

Decrypt a file

```bash
gpg -d file.txt.gpg            # to show content directly in bash or
gpg -d file.txt.gpg > file.txt # to create decrypted file
```

## SSH

Add existing private SSH key to bash

```bash
chmod 600 private.key # set permissions to be only read-writable by me
eval $(ssh-agent -s)  # start ssh agent in background
ssh-add private.key   # add SSH private key to bash
```

## PDF

Count the words of a PDF file:

```bash
pdftotext myfile.pdf - | wc -w
```

## Password Generation

Quickly create a random string to use for passwords:

```bash
date +%s | sha256sum | base64 | head -c 32 ; echo
```

## Get public IP address

```bash
curl ipinfo.io/ip
```

## MySQL

Run database import file on server (corresponding to the phpMyAdmin importer)

```bash
mysql -u database_user -p database_name < file.sql
mysql -u database_user -p -h database_host database_name < file.sql # if it's not localhost
```

Create database export file

```bash
mysqldump -u database_user -p database_name > file.sql
```

## Line Endings

Convert all PHP files in the current directory to Unix line endings

```bash
find "./" -type f -name '*.php' -execdir dos2unix {} +
```

## Python

Update all outdated packages at once

```bash
pip list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U 
```
