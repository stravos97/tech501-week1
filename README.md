
# Week 1 learning

- [Week 1 learning](#week-1-learning)
  - [How Markdown works](#how-markdown-works)
    - [This is a subheading](#this-is-a-subheading)
      - [Bullet Points](#bullet-points)
      - [Numbered steps](#numbered-steps)
      - [Bold and italics](#bold-and-italics)
      - [Images](#images)
      - [Links](#links)
  - [How git works](#how-git-works)

##  How Markdown works
### This is a subheading

#### Bullet Points

-- Used when sequence is NOT important

* Point 1
    * sub point 1
    * sub point 2
        * sub-sub point 1
        * sub-sub point 2
* Point 2

- Point 1
- Point 2


#### Numbered steps

- Number it if it's steps

1. First instruction
2. Seconf instruction
    1. Sub step 1
    2. Sub step 2
        * Point for Sub step 2
        * Point 2 for Sub step 2

<br>

#### Bold and italics

* CTRL + B - **bold**
* CTRL + I - *italics*


#### Images

* Have a images directory and drag images into that dir. then drag them from that dir into the Markdown file
    * Drag + Drop + SHIFT

![alt text](images/13429_ILL_DevOpsLoop.png)

#### Links

Click [here](http://google.com)


## How git works

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
