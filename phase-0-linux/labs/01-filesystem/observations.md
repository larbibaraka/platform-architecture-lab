# Observations - Filesystem Structure Lab

## Observation 1

Each linux command is defined with this structure `command [options] [arguments]` where the options are used to modify the behavior of the command and the arguments are used to specify the target of the command.

## Observation 2

The `ls` command is used to tell us the content of a directory but some directories can not be accessed by any user only the owner of the directory can access it. For example, the `/root` directory is only accessible by the root user.

## Observation 3

The `less` command falls into a class of programs called pagers, unlike `more`, `less` can allow us to go page forward and backward.

## Observation 4

The Linux filesystem hierarchy is organized in a tree-like structure with the root directory `/` at the top. Each directory has a specific purpose and contains files and subdirectories related to that purpose. Here are some of the key directories in the Linux filesystem hierarchy:

- `/` is the root directory.
- `/bin` This directory contains binaries or programs that must be present in order for the system to boot and run.
- `/home` This directory contains the home directories of all users on the system.
- `/usr` This directory contains user programs and data that are not essential for the system to boot or run.
- `/boot` Contain the linux kernel
- `/dev` Unlike what it name suggests, this is a special directory that contain device nodes that represent hardware devices and virtual devices on the system.
- `/etc` This directory contains system configuration files.
- `/lib` This directory contains shared libraries that are used by programs on the system.
- `/media` On modern Linux systems, this directory is used for mounting removable media such as USB drives and CD-ROM
- `/mnt` This directory is used for temporarily mounting filesystems.
- `/opt` This directory is used for installing optional software packages.
- `/proc` This is a virtual filesystem meaning that it does not exist on disk but is created in memory, providing information about the system and running processes.
- `/sbin` This directory contains system binaries that are used for system administration tasks.
- `/tmp` This directory is used for storing temporary files.
- `/var` The /var directory tree is where data that is likely to change is stored. Various databases, spool files, user mail, and so forth, are located here.

## Observation 5

Unlike many propritary systems, Linux makes everything available for examination and study.

## Obervation 6

`cp`,`mv`,`mkdir`,`rm`,`ln` are the most frequently used commands on linux.

## Observation 7

To be honnest when working with graphical interface these commands seems to be a wast of time but when i know the powerful options they provide i can not imagine how i can do the same thing with a graphical interface. For example, the `cp` command with the `-r` option allows us to copy directories and their contents recursively, which is much faster than copying each file individually using a graphical interface. or for example when you want to copy all the files from one directory to another but copy only the files that do not exist in the destinatoion directory or are newer than the versions in the destibnaion directory you can use the `cp` command with the `-u` option which stands for update, this will only copy the files that are newer than the versions in the destination directory or do not exist in the destination directory. This is a very powerful option that can save us a lot of time when we want to keep our files up to date.

### cp Command :

```bash
cp -u *.txt /path/to/destination/
```

## Observation 8

In Linux, a file is not just a name. Internally, every file is represented by a data structure called an inode.

The inode stores important metadata about the file, including:

- file size
- file owner
- file permissions
- timestamps (creation, modification, access)
- pointers to the disk blocks where the file data is stored

Interestingly, the inode does not store the filename. The filename is stored in the directory and simply points to the inode.

This explains several Linux behaviors:

- Multiple filenames can point to the same inode (hard links).
- A program can continue running even if its file is deleted, because the process still references the inode.
- A filesystem can run out of inodes even if disk space is still available.

To view inode numbers, we can use the following command:

ls -i

Example:

touch file1
ln file1 file2
ls -i

Both files will show the same inode number, meaning they reference the same underlying file data.
