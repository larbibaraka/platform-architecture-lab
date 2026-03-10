# Notes — Lab 1: Filesystem Structure & Basic File Manipulation

## Introduction

This lab explores the structure of the Linux filesystem and the basic commands used to navigate and manipulate files and directories.

Understanding how the filesystem is organized is one of the most important foundations for working with Linux systems, especially for system administration, DevOps, and platform engineering.

---

# 1. Command Structure in Linux

Most Linux commands follow a common structure:

command [options] [arguments]

| Component | Description                                       |
| --------- | ------------------------------------------------- |
| command   | The program we want to execute                    |
| options   | Flags that modify how the command behaves         |
| arguments | The target of the command (file, directory, etc.) |

Example:

ls -l /home

Explanation:

- ls → command used to list directory contents
- -l → option enabling long format output
- /home → argument specifying the directory

---

# 2. Linux Filesystem Hierarchy

Linux organizes files using a hierarchical tree structure.

At the very top is the root directory:

/

All files and directories exist somewhere under this root.

Example structure:

/
├── bin
├── boot
├── dev
├── etc
├── home
│ └── user
├── lib
├── media
├── mnt
├── opt
├── proc
├── sbin
├── tmp
├── usr
└── var

Each directory serves a specific purpose in the operating system.

---

# 3. Important Linux Directories

| Directory | Purpose                                    |
| --------- | ------------------------------------------ |
| /         | Root directory                             |
| /bin      | Essential user binaries                    |
| /boot     | Kernel and bootloader files                |
| /dev      | Device files representing hardware         |
| /etc      | System configuration files                 |
| /home     | User home directories                      |
| /lib      | Shared libraries                           |
| /media    | Mount points for removable media           |
| /mnt      | Temporary mount points                     |
| /opt      | Optional third-party software              |
| /proc     | Virtual filesystem for process information |
| /sbin     | System administration binaries             |
| /tmp      | Temporary files                            |
| /usr      | User applications and programs             |
| /var      | Variable data such as logs                 |

Examples:

- /etc contains system configuration files
- /var/log stores system logs
- /home contains user directories

---

# 4. Navigating the Filesystem

Several commands allow us to move through the filesystem.

## Print Current Directory

pwd

Displays the current working directory.

Example output:

/home/user/projects

---

## Change Directory

cd directory

Examples:

cd /home/user
cd ..
cd ~
cd -

| Command | Meaning                      |
| ------- | ---------------------------- |
| cd      | Go to home directory         |
| cd ..   | Move up one directory        |
| cd ~    | Go to home directory         |
| cd -    | Return to previous directory |

---

# 5. Listing Directory Contents

The ls command displays files and directories.

Basic usage:

ls

Common options:

ls -l
ls -a
ls -A
ls -h
ls -S
ls -t

| Option | Description                       |
| ------ | --------------------------------- |
| -l     | Long format listing               |
| -a     | Show hidden files                 |
| -A     | Show hidden files except . and .. |
| -h     | Human readable file sizes         |
| -S     | Sort by file size                 |
| -t     | Sort by modification time         |

Example output:

-rw-r--r-- 1 user user 4096 Jun 10 file.txt

This shows:

- file permissions
- number of links
- file owner
- group
- file size
- modification date
- filename

---

# 6. Viewing File Contents

Two useful commands help inspect files.

## file

file filename

Determines the type of file.

Example:

file script.sh

Output:

script.sh: Bourne-Again shell script

---

## less

less filename

Used to view file contents page by page.

Advantages of less:

- scroll forward
- scroll backward
- search inside files

It is very useful when reading large files such as logs.

---

# 7. File and Directory Manipulation

Linux provides powerful commands to manage files.

## Create Directories

mkdir directory_name

Example:

mkdir projects

---

## Copy Files

cp source destination

Example:

cp file.txt backup.txt

Useful options:

cp -r directory destination
cp -u source destination
cp -i source destination
cp -v source destination
cp -p source destination
cp -a directory destination

| Option | Description                         |
| ------ | ----------------------------------- |
| -r     | Copy directories recursively        |
| -u     | Copy only if source is newer        |
| -i     | Ask before overwriting              |
| -v     | Show verbose output                 |
| -p     | Preserve file attributes            |
| -a     | Archive mode (preserves everything) |

---

## Move or Rename Files

mv source destination

Example:

mv file.txt newfile.txt

Options:

mv -i
mv -v

---

## Remove Files

rm file

Examples:

rm file.txt
rm -r directory

Important options:

rm -r
rm -i
rm -v

⚠ Be careful with rm because deletion is permanent.

Example difference:

rm \*.html

Removes all HTML files.

rm \* .html

Removes all files, then attempts to remove .html.

---

# 8. Links in Linux

The ln command creates links between files.

Two types exist.

## Hard Links

ln file1 file2

Both files point to the same inode and same data.

---

## Symbolic Links

ln -s file1 linkname

A symbolic link is a pointer to another file.

---

# 9. Power of the Command Line

Although graphical interfaces make some tasks easier, the command line provides several advantages:

- speed
- automation
- scripting capabilities
- powerful options

Example:

cp -u \*.txt /destination/

This command copies only files that:

- do not exist in the destination
- are newer than the destination version

This makes it extremely useful for keeping directories synchronized.

---

# Conclusion

This lab introduced the Linux filesystem structure and the basic commands used to navigate and manipulate files.

Key takeaways:

- Linux organizes files in a hierarchical structure starting at /
- Commands follow a consistent structure
- The command line provides powerful tools for file management
- Understanding these fundamentals is essential for mastering Linux

These concepts form the foundation for deeper Linux knowledge, including permissions, processes, and system administration.
