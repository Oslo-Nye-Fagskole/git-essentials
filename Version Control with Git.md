# Version control with Git

Version control is a way to track changes in files over time, allowing you to go back to earlier versions when needed and to collaborate with others safely. **Git** has become the de facto standard for version control, used by developers worldwide.

In this activity, you will create a new Git repository and make a series of commits to it, checking the status and log of your work as you progress, and revert changes to restore previous versions.


## Steps

Imagine your Git repository as a container for your Warhammer army roster. Let's start by creating the necessary folder and adding a few unit lists. Make sure you have [Git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) on your machine!

Once you have Git installed, it’s time to begin, so *“Into the fires of battle, unto the anvil of war!”*

1. Create a new folder called **Warhammer40K**

2. Inside the **Warhammer40K** folder, initialize a new Git repository

3. Make a file called **infantry.txt** ⚔️ and another called **vehicles.txt** 🚙

4. Check the status of your repository: verify that the newly created files are *"Untracked files"*

5. Add both files to your repository and make a commit that includes them both, with a message saying *"Added initial Warhammer units"*

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

9. Make a second commit including *only* the changes from **vehicles.txt**, with a commit message saying *"Added vehicle detachment"*

10. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and only 3 log entries reflecting the changes done so far

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

13. Check the status of your repository: verify the new changes as *"Changes not staged for commit"* and still only 3 log entries (we haven't committed any changes since the last time we checked!)

14. Stage and commit both files with a **single operation**, with a commit message saying *"Roster reinforced with new units"*

15. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and 4 log entries reflecting all changes done so far, including the new entry reflecting our latest commit

16. Change **vehicles.txt** only, add a bad unit *"Broken Land Speeder"* and commit the change with a message saying *"Added unreliable vehicle"*

17. Check the status of your repository: verify there are no pending changes (*"nothing to commit, working tree clean"*) and 5 log entries reflecting all changes done so far, including the new entry reflecting our mishap 💥

18. Since we don’t want unreliable units in our roster, we’d better remove that last commit! Remove the previous commit completely from your repository and its history. **No one must know!**

19. Check the status of your repository: verify there are no pending changes and **no log entry** indicating we ever added the broken unit.

Well done, we have our reinforced army roster ready and have removed all trace of our bad decision 🥳

## Optional

Perform the *"Broken Land Speeder"* exercise again, but this time with the infantry file. Stage and commit the bad unit *"Warp-tainted cultists"* and then immediately realize your decision was regrettable. Given that we’re now **obligated by law** to keep a record of all changes, regardless of any alterations to the roster later, use the appropriate Git command to undo your last commit while maintaining a history of all changes.

What does the Git history log show now?
