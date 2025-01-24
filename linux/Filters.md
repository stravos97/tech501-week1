# Filters

Filters in Linux are commands that process text streams and produce output that can be used in further processing. They are an integral part of shell scripting and command-line operations, especially when working with pipelines (`|`), where the output of one command is used as input for another.

## `cat`: Concatenate and Display Files

The `cat` command reads files sequentially, writing their contents to the standard output. It’s often used to display the contents of files or to concatenate multiple files into one.

### Basic Usage

- **Display a File**: 

    ```bash
    cat filename
    ```

- **Concatenate Multiple Files**: 

    ```bash
    cat file1 file2 > combinedfile
    ```

## `grep`: Search Text Using Patterns

The `grep` command searches through text using patterns (regular expressions). It’s commonly used to find specific lines in a file that match a pattern.

### Basic Usage

- **Search for a Pattern in a File**:

    ```bash
    grep "pattern" filename
    ```

- **Search Recursively in a Directory**:

    ```bash
    grep -r "pattern" directory/
    ```

## Combining Filters

Filters can be combined using pipes (`|`) to perform more complex text processing tasks.

