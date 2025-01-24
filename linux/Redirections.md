# Redirections

Redirection in Linux allows you to control where the output of a command goes and where the input for a command comes from. This is a fundamental aspect of shell scripting and command-line operations, enabling users to connect and manipulate data streams efficiently.

This page will cover the basics of standard input/output (I/O), redirection operators, and how to combine them with pipes to perform powerful data manipulations.

## Redirecting Standard Output (`>` and `>>`)

Redirecting output is one of the most common forms of redirection.

### Basic Redirection (`>`)

- **Redirect Output to a File**:

    ```bash
    command > file.txt
    ```

    This command sends the output to `file.txt`, overwriting it if the file exists.

### Append Output (`>>`)

- **Append Output to a File**:

    ```bash
    command >> file.txt
    ```

    This command appends the output to `file.txt` without overwriting the existing content.

## Redirecting Standard Input (`<`)

Redirecting input allows a command to take input from a file instead of the keyboard.

- **Use a File as Input**:

    ```bash
    command < file.txt
    ```

    This feeds the contents of `file.txt` as input to the command.


- **Redirect Output and Error Separately**:

    ```bash
    command > output.txt 2> error.log
    ```

    This sends standard output to `output.txt` and errors to `error.log`.

## Using Pipes (`|`)

Pipes allow you to use the output of one command as the input for another.

- **Basic Pipe Usage**:

    ```bash
    command1 | command2
    ```

    This takes the output of `command1` and uses it as the input for `command2`.

### Example: Using Pipes with Redirection

- **Search for a Word in a File and Count Occurrences**:

    ```bash
    grep "word" file.txt | wc -l
    ```

    This command finds all occurrences of "word" in `file.txt` and then counts the number of matching lines.

