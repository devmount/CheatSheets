# cmd

## Symlink

Create a symbolic link e.g. for XAMPP's htdocs directory:

```cmd
mklink /D symlink-name c:\Users\user\data\git\project\
```

Note: The `/D` is there because we are linking to a directory. `symlink-name` is the name of the symbolic link. Finally, the path is where the symbolic link actually resolves to.
