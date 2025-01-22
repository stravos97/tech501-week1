# How git works

1. **Repository Initialization**:
    - To start tracking a project with Git, it first needs to be initialised
     ```bash
     git init
     ```
    - This creates a hidden `.git` directory, storing all of the necessary changes

2. **Staging Changes**:
   - Before commiting changes, they need to be staged:
    ```bash
     git add .
     ```

   - Staging allows you to select which changes to include in the next commit.

3. **Committing Changes**:
   - After staging, commit the changes to the repository:
     ```bash
     git commit -m "Descriptive commit message"
     ```

4. **Viewing Git changes**:
   - To see the status:
     ```bash
     git status
     ```

5. **Branching and Merging**:
   - **Switching to the Main branch**:
    ```bash
     git branch -M main
     ```
