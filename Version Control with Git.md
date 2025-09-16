# Version control with Git

Version control is a way to track changes in files over time, allowing you to go back to earlier versions when needed and to collaborate with others safely. **Git** has become the de facto standard for version control, used by developers worldwide.

In this activity, you will create a new Git repository and make a series of commits to it. Along the way, you will check the status of your work and practice reverting changes when necessary.

## Steps

Imagine your Git repository as a container for your Warhammer army roster. Let's start by creating the necessary folder and adding a few files to hold our unit lists. Make sure you have [Git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) on your machine!

Once you have Git installed, it's time to begin, so *“Into the fires of battle, unto the anvil of war!”*

1. Create a new folder called **Warhammer40K**

2. Inside the **Warhammer40K** folder, initialize a new Git repository
    ```
    git init
    ```

3. Make a file called **infantry.txt** ⚔️ and another called **vehicles.txt** 🚙

4. Check the status of your repository: verify that the newly created files are *"Untracked files"*
    ```
    git status
    ```

5. Add both files to your repository and make a commit that includes them both, with a message saying *"Added initial Warhammer units"*
    ```
    git add infantry.txt vehicles.txt
    git commit -m "Added initial Warhammer units"
    ```

6. In the **infantry.txt** file, add the following units:
    ```
    Space Marines (5)
    Scout Squad (10)
    ```

7. In the **vehicles.txt** file, add the following units:
    ```
    Rhino Transport
    Predator Tank
    ```

8. Make a new commit, including *only* the changes from **infantry.txt**, with a commit message saying *"Added infantry squads"*
    ```
    git add infantry.txt
    git commit -m "Added infantry squads"
    ```

9. Make a second commit including *only* the changes from **vehicles.txt**, with a commit message saying *"Added vehicle detachment"*
    ```
    git add vehicles.txt
    git commit -m "Added vehicle detachment"
    ```

10. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and only 3 log entries reflecting the changes done so far
    ```
    git status
    git log --oneline
    ```

11. Change both files, adding a few new units to strengthen your roster

**infantry.txt**:
    
    Space Marines (5)
    Scout Squad (10)
    Terminator Squad (3)
    Assault Marines (5)

**vehicles.txt**:

    Rhino Transport
    Predator Tank
    Land Raider
    Dreadnought

12. Use Git to check and review modifications to the files: verify the new units are visible as changes made
    ```
    git diff
    ```

13. Check the status of your repository: verify the new changes as *"Changes not staged for commit"* and still only 3 log entries (we haven't committed any changes since the last time we checked!)
    ```
    git status
    ```

14. Stage and commit both files with a **single operation**, with a commit message saying *"Roster reinforced with new units"*
    ```
    git add .
    git commit -m "Roster reinforced with new units"
    ```

15. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and 4 log entries reflecting all changes done so far, including the new entry reflecting our latest commit
    ```
    git status
    git log --oneline
    ```

16. Change **vehicles.txt** only, add a bad unit *"Broken Land Speeder"* and commit the change with a message saying *"Added unreliable vehicle"*
    ```
    git commit -am "Added unreliable vehicle"
    ```

17. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and 5 log entries reflecting all changes done so far, including the new entry reflecting our mishap 💥
    ```
    git status
    git log --oneline
    ```

18. Since we don't want unreliable units in our roster, we'd better remove that last commit! Remove the previous commit completely from your repository and its history. **No one must know!**
    ```
    git reset --hard HEAD~1
    ```

19. Check the status of your repository: verify there are no pending changes and **no log entry** indicating we ever added the broken unit.
    ```
    git status
    git log --oneline
    ```

Well done, we have our reinforced army roster ready and have removed all trace of our bad decision 🥳

## Optional

Perform the *"Broken Land Speeder"* exercise again, but this time with the infantry file. Stage and commit the bad unit *"Warp-tainted cultists"* and then immediately realize your decision was regrettable. Given that we're now **obligated by law** to keep a record of all changes, regardless of any alterations to the roster later, use the appropriate Git command to undo your last commit while maintaining a history of all changes.

What does the Git history log show now?
