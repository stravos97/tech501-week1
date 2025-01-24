# Terminal Basics

## Navigating the File System

The Linux file system is organized in a hierarchical structure with directories (folders) and files. Here are some basic commands for navigating the file system:

- **`pwd` (Print Working Directory)**: Displays the current directory you are in.
  
  ```bash
  pwd
  ```

- **`ls` (List)**: Lists the files and directories in the current directory.

  ```bash
  ls
  ```

  - `ls -l`: Lists files in long format, showing details like permissions, ownership, and size.
  - `ls -a`: Lists all files, including hidden files (those starting with a `.`).

- **`cd` (Change Directory)**: Changes the current directory to the specified directory.

  ```bash
  cd /path/to/directory
  ```

  - `cd ..`: Moves up one directory level.
  - `cd ~`: Moves to the home directory.
  - `cd -`: Switches to the previous directory.

## Managing Files and Directories

In the terminal, you can create, move, copy, and delete files and directories using the following commands:

- **`touch`**: Creates an empty file or updates the timestamp of an existing file.

  ```bash
  touch filename.txt
  ```

- **`mkdir` (Make Directory)**: Creates a new directory.

  ```bash
  mkdir new_directory
  ```

- **`cp` (Copy)**: Copies files or directories.

  ```bash
  cp source_file destination_file
  ```

  - `cp -r source_directory destination_directory`: Copies directories recursively.

- **`mv` (Move)**: Moves or renames files and directories.

  ```bash
  mv old_name new_name
  ```

  - This command can be used to rename a file or move it to a different directory.

- **`rm` (Remove)**: Deletes files.

  ```bash
  rm filename.txt
  ```

  - `rm -r directory_name`: Deletes directories and their contents recursively. Be cautious when using this command, as it permanently removes files.

- **`rmdir` (Remove Directory)**: Deletes an empty directory.

  ```bash
  rmdir empty_directory
  ```

## Viewing and Editing Files

Linux provides several tools for viewing and editing files directly from the terminal:

- **`cat` (Concatenate)**: Displays the contents of a file.

  ```bash
  cat filename.txt
  ```

- **`less`**: Opens a file for viewing one page at a time.

  ```bash
  less filename.txt
  ```

  - Press `q` to quit.

- **`nano`**: A simple text editor for editing files directly in the terminal.

  ```bash
  nano filename.txt
  ```

  - Use `Ctrl + X` to exit, `Y` to save changes, and `N` to discard changes.


## Useful Shortcuts

The terminal supports several shortcuts that can help you work more efficiently:

- **`Ctrl + C`**: Interrupts or cancels the current command.
- **`Ctrl + D`**: Logs out of the current shell session or closes the terminal.
- **`Ctrl + L`**: Clears the terminal screen (similar to the `clear` command).
- **`Tab`**: Autocompletes commands, file names, or directories.

## Command History

The terminal keeps a history of the commands you’ve entered, which you can use to save time:

- **`history`**: Displays a list of previously executed commands.

  ```bash
  history
  ```

- **`!n`**: Re-runs the command numbered `n` in the history.

  ```bash
  !42
  ```

- **`!!`**: Repeats the last command.

  ```bash
  !!
  ```

- **Arrow Keys**: Use the up and down arrow keys to navigate through your command history.

## Getting Help

Linux provides several ways to get help and learn more about commands:

- **`man` (Manual)**: Displays the manual page for a command, providing detailed information on its usage.

  ```bash
  man ls
  ```

- **`--help`**: Most commands offer a `--help` option to display a brief overview of how the command works.

  ```bash
  ls --help
  ```
