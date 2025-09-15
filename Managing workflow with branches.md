# Managing workflow with branches

Branching in Git lets us explore new ideas, add features, or fix mistakes without without affecting the main branch of our project. There are several ways to organize branching, a few common ones being:

- **Git Flow**: multiple long-lived branches for features, releases, and fixes.
- **Trunk-based development**: very short-lived branches merged quickly.
- **GitHub Flow**: short feature branches created from `main` and merged back in once complete.

For now, we’ll use the **GitHub Flow** style, since it’s simple and keeps `main` stable while we experiment on the side. Let’s put this into practice with our Warhammer army roster ⚔️

## Preparing the battlefield

1. Make sure you are in your **Warhammer40K** repository from earlier.
   ```bash
   cd Warhammer40K
   git status
   ```

2. Ensure you’re on the `main` branch before starting:
   ```bash
   git checkout main
   ```

3. Create a branch for a new feature: let’s add **Elite Units**:
   ```bash
   git checkout -b add-elites
   ```

4. Create another branch for a quick fix: we spotted a mistake in the infantry list:
   ```bash
   git checkout main
   git checkout -b fix-infantry
   ```

At this point you have two branches to work on: one for a fix, one for reinforcements.

## First priority: fixing mistakes 🛠️

1. Make sure you are working on the `fix-infantry` branch:
   ```bash
   git checkout fix-infantry
   ```

2. Edit **infantry.txt**: remove the unreliable unit *“Warp-tainted cultists”* and replace it with *“Imperial Guard Squad (10)”*.

3. Stage and commit your fix:
   ```bash
   git add infantry.txt
   git commit -m "Corrected infantry roster"
   ```

4. Merge the fix back into `main`:
   ```bash
   git checkout main
   git merge fix-infantry
   ```

Check your log: the fix is now part of `main`.


## Adding reinforcements 🚀

1. Switch to the `add-elites` branch:
   ```bash
   git checkout add-elites
   ```

2. Add new units to **infantry.txt**:
   ```
   Terminator Squad (5)
   Vanguard Veterans (5)
   ```

3. Stage and commit your changes:
   ```bash
   git add infantry.txt
   git commit -m "Added elite infantry units"
   ```

4. Merge the latest `main` into your branch before continuing:
   ```bash
   git merge main
   ```

## The clash ⚡

Because both the fix branch and the elites branch modified **infantry.txt**, Git will raise a **merge conflict** when merging `main` into `add-elites`.

Open the file and you’ll see conflict markers:

* The `main` branch shows the corrected infantry squad (*Imperial Guard Squad*).
* Your branch shows the elite additions.

## Resolving the conflict

1. Open **infantry.txt** in your editor.
2. Remove the conflict markers and keep both the corrected squad and your new elites.
3. Save the file.

Then stage and commit the resolution:

```bash
git add infantry.txt
git commit -m "Resolved merge conflict: kept fix and elites"
```

## Securing victory 🎉

1. Switch back to `main`:
   ```bash
   git checkout main
   ```

2. Merge the `add-elites` branch into `main`:
   ```bash
   git merge add-elites
   ```

3. Verify the log and contents of **infantry.txt**: your roster should now include both the corrected squad *and* the new elite units.

4. Clean up by deleting the branches:
   ```bash
   git branch -d fix-infantry
   git branch -d add-elites
   ```
