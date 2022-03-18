# cmd

## Symlink

Create a symbolic link e.g. for XAMPP's htdocs directory:

```cmd
mklink /D symlink-name c:\Users\user\data\git\project\
```

Note: The `/D` is there because we are linking to a directory. `symlink-name` is the name of the symbolic link. Finally, the path is where the symbolic link actually resolves to.

## Free Port 80

Windows sometimes blocks port 80 due to the HTTP Service, which can be stopped with the following command to make port 80 locally available e.g. for WinNMP, wamp or XAMPP.

```cmd
net stop http
```
