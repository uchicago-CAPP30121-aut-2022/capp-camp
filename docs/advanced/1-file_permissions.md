---
layout: default
title: Linux File Permissions
nav_order: 1
parent: Advanced
---

# File Permissions

Sometimes we want to restrict who can access certain resources on the Linux file system.

Most file systems assign "File Permissions" (or just permissions) to specific users and groups of users. Unix-type systems are no different. File permissions dictate who can read (view), write (create/edit), and execute (run) files on a file system.

All directories and files are owned by a user. Each user can be a member of one or more groups. To see your groups, enter the command `groups` into the command line.

## Scopes and Permissions

File permissions in Unix systems are managed in three distinct scopes. Each scope has a distinct set of permissions.

**User** - The owner of a file or directory makes up the user scope.

**Group** - Each file and directory has a group assigned to it. The members of this group make up the group scope.

**Others** - Every user who does not fall into the previous two scopes make up the others scope.

If a user falls into more than one of these scopes, their effective permissions are determined based on the first scope the user falls within in the order of user, group, and others.

Each scope has three specific permissions for each file or directory:

**read** - The read permission allows a user to view a file’s contents. When set for a directory, this permission allows a user to view the names of files in the directory, but no further information about the files in the directory. `r` is shorthand for read permissions.

**write** - The write permission allows a user to modify the contents of a file. When set for a directory, this permission allows a user to create, delete, or rename files. `w` is shorthand for write permissions.

**execute** - The execute permission allows a user to execute a file (or program) using the operating system. When set for a directory, this permission allows a user to access file contents and other information about files within the directory (given that the user has the proper permissions to access the file). The execute permission does not allow the user to list the files inside the directory unless the read permission is also set. `x` is shorthand for execute permissions.

## Viewing File Permissions

To list information about a file, including its permissions, type:

```bash
ls -l <filepath>
```

You’ll get output of the form:

```bash
<permissions> 1 owner group <size in bytes> <date modified> <filepath>
```

For example, if we want information on `/usr/bin/python3.8`:

```bash
$ ls -l /usr/bin/python3.8
-rwxr-xr-x 1 root root 5486384 Jan 27  2021 /usr/bin/python3.8
```

The first thing we can notice is that the owner of the file is a user named `root`. (FYI, `root` is a name for an account that has access to all commands and files on a Linux system. Other accounts may also have "root" privileges.) The file's group is also `root`.

The permissions are `-rwxr-xr-x`. The initial dash (`-`) indicates that `/usr/bin/python3.8` is a file, not a directory. Directories have a `d` instead of a dash. Then the permissions are listed in `user`, `group`, and `others` order. In this example, the owner, `root`, can read (`r`), write (`w`), and execute (`x`) the file. Users in the `root` group and all other users can read and execute the files.

By default, any files or directories that you create will have your username as both the user and the group. (If you run `groups`, you’ll notice that there is a group with the same name as your username. You are the only member of this group.) On our Linux machines, by default, new files are given read and write permissions to user and group and no permissions to other. New directories will be set to have read, write and execute permissions for user and group.

### Checkpoint

Verify this claim by running `ls -l backups/copy2.txt` and `ls -ld backups` in your `capp_camp/lab1` directory from the first lab.

The `-d` flag tells `ls` to list the directory, instead of its contents. Notice that the first letter in the permissions string for `backups` is a _d_, while it is a `-` for `backups/copy2.txt`.

Once you have verified the claim, go ahead and remove the `backups` directory.

## Changing Permissions, Owner, and Group

|   |   |
|---|---|
|`chmod <permissions> <path-name>`|Set the permissions for a file/directory.| 
|`chmod <changes> <path-name>`|Update the permissions for a file/directory.|  
|`chown <username> <path-name>`|Change the owner of a file to username.|  
|`chgrp <group> <path-name>`|Change the group of a file.|  
|`cat <path-name>`|Print the contents of a file to the terminal.|  

To change permissions, we use the `chmod` command. There are two ways to specify the permissions. We’ll describe the more accessible one first: to set the permissions you specify the scope using a combination of `u`, `g`, and `o`; the permission using `r`, `w`, and `x`; and either `+` or `-` to indicate that you want to add or remove a permission. For example `uo+rw` indicates that you want to add read and write permissions for the user and others scopes.

We can demonstrate this using the `cat` command to print file contents to the terminal:

```bash
$ echo "Hello!" > testfile
$ ls -l testfile
-rw-rw---- 1 username username 7 Aug 23 11:22 testfile
$ cat testfile
Hello!
$ chmod ug-r testfile   #remove read permissions from user and group
$ ls -l testfile
--w--w---- 1 username username 7 Aug 23 11:22 testfile
$ cat testfile
cat: testfile: Permission denied
$ chmod u+r testfile    #give user scope read permissions
```

In this last example, we have added user read permissions to `testfile`.

In addition to the symbolic method for setting permissions, you can also use a numeric method: each permission has a unique value: read = 4, write = 2, execute = 1. As a result, you can describe the permissions of each scope using the sum of its permissions’ values. For example, if a file has read and write permissions for the user scope, its permissions can be described as 6 (4 + 2 = 6).

You can describe the permissions of a file overall using these values for each scope. For example, 761 describes the permissions for a file with read, write, and execute permissions for the user scope, read and write permissions for the group scope, and only execute permissions for the others scope.

The symbolic approach is relative: it allows you to add and remove permissions relative the the current file permissions. The numeric method is absolute: it sets the permissions to a specific configuration. We recommend starting the symbolic approach. It is easier to get right. As you get more comfortable with setting permissions, it is useful to learn how to use the numeric method.

To change the owner of a file or directory (if you are the owner or root), use the command:

```bash
chown <new owner> <path to file>
```

To change a file’s group (if you are the owner or root), use the command:

```bash
chgrp <new group> <path to file>
```

It is unlikely that you will need to use these two commands for this course.

## Exercises

1. Run `echo "Hello!" > testfile` to construct `testfile`. Look at the permissions using `ls -l`.

2. Change the permissions on `testfile` to allow "read" access for others. Run `ls -l testfile` to check the new permissions.

3. Remove group write access from `testfile`. Check the corrected permissions.

4. Remove `testfile`.
