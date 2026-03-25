# Observations - Permissions

## Observation 1

unix operating systems are by design multi user + multi tasking and this is not a new thing But rather a feature embaded deeply into the design of the Os and this is why we have the concept of permissions and ownership in unix based systems

## Observation 2

each user created gets an UID and a GID to see it we somply hit : `id` in the terminal and we can see the UID and GID of the user

## Observation 3

`/etc/passwd` users accrounts defined in this file and we can see the UID and GID of each user in this file
`/etc/group` groups are defined in this file and we can see the GID of each group in this file

## Observation 4

when a user is created the passwd & group are modified along with `/etc/shadow` file which contains the encrypted password of the user and other password related information

## Observation 5

each file or directory has : read access, write access, and execute access

## Observation 6

permissions are represented in 3 sets of 3 characters each for user, group, and others

## Observation 7

permissions can be represented in octal notation where read is 4, write is 2, and execute is 1. For example, `rwx` is 7 (4+2+1), `rw-` is 6 (4+2), and `r--` is 4 (4).

## Observation 8

the `umask` command is used to set default permissions for newly created files and directories.

## Observation 9

the `chmod` command is used to change the permissions of a file or directory. It can be used with symbolic notation (e.g., `chmod u+x file`) or octal notation (e.g., `chmod 755 file`).

## Observation 10

the `chown` command is used to change the owner of a file or directory, while the `chgrp` command is used to change the group ownership of a file or directory.

## Observation 11

the `su` command allows you to switch to another user account, while the `sudo` command allows you to execute a command as another user, typically the superuser (root).

## Observation 12

the `passwd` command is used to change a user's password. It can be used by the user themselves or by the superuser to change another user's password.

## Observation 13

the 3 special permissions in linux are : setuid, setgid, and sticky bit

- setuid allows a user to execute a file with the permissions of the file owner : `u+s`
- setgid allows a user to execute a file with the permissions of the file's group : `g+s`
- sticky bit allows only the owner of a file or directory to delete or rename it, even if other users have write permissions on it. This is commonly used on directories like `/tmp` to prevent users from deleting or renaming files created by other users. `+t`
- these special permissions can be set using the `chmod` command with symbolic notation (e.g., `chmod u+s file` for setuid) or octal notation (e.g., `chmod 4755 file` for setuid).
