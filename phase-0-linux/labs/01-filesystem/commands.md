# Commands Used — Filesystem Structure Lab

This file lists the commands used to explore the Linux filesystem hierarchy.

---

## Commands

```bash
pwd # Print the current working directory
cd # Change directory
ls # List the contents of a directory
file # Determine the type of a file
less # View the contents of a file one page at a time
cp  # Copy files and directories
mv  # Move or rename files and directories
mkdir # Create directories
rm # Remove files and directories
ln # Create links between files (hard links and symbolic links)
```

### cd Command :

- `cd ` : Changes the working directory to your home directory.
- `cd -` : Chnages the working directory to the previous working directrory.
- `cd ~user_name ` : Changes the worknig directory to the home directory of the specified user.

### ls Command :

- `ls -l` : Lists files in long format, showing permissions, ownership, size, and modification date.
- `ls -a` : Lists all files, including hidden files (those starting with a dot).
- `ls -A` : Lists all files, including hidden files, but excluding `.` and `..`.
- `ls -h` : Displays file sizes in human-readable format (e.g., KB, MB).
- `ls -S` : Sorts files by size, with the largest files listed first.
- `ls -t` : Sorts files by modification time, with the most recently modified

### less Command :

- `less filename` : Opens the specified file in the less pager, allowing you to scroll through the contents.

### cp Command :

- `cp source_file destination_file` : Copies a file from the source to the destination.
- `cp -r source_directory destination_directory` : Copies a directory and its contents recursively.
- `cp -u source_file destination_file` : Copies the file only if the source file is newer than the destination file or if the destination file does not exist.
- `cp -i source_file destination_file` : Prompts for confirmation before overwriting an existing file at the destination.
- `cp -v source_file destination_file` : Displays verbose output, showing the files being copied.
- `cp -p source_file destination_file` : Preserves the file's attributes (such as permissions and timestamps) when copying.
- `cp -a source_directory destination_directory` : Archives the directory, preserving all attributes and copying recursively.

### mv Command :

- `mv source_directory destination_directory` : Moves or renames a directory from the source to the destination.
- `mv -i source_file destination_file` : Prompts for confirmation before overwriting an existing file at the destination.
- `mv -v source_file destination_file` : Displays verbose output, showing the files being moved or renamed.

### rm Command :

> **Note : I need to be very careful when using the `rm` command because `rm *.html` is not the same as `rm * .html` the first delete all files with .html and the second delete all files and then delete files with .html.**

- `rm file` : Removes the specified file.
- `rm -r directory` : Removes a directory and its contents recursively.
- `rm -i file` : Prompts for confirmation before removing the specified file.
- `rm -v file` : Displays verbose output, showing the files being removed.
