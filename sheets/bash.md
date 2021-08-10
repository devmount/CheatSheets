# Bash

## Compression

Create a .tar.gz file

```bash
tar -czvf file.tar.gz directory-to-compress/
```

Extract contents of a .tar.gz file

```bash
tar -zxvf file.tar.gz
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
```

Create database export file

```bash
mysqldump -u database_user -p database_name > file.sql
```
