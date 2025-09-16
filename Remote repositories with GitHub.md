# Remote repositories with GitHub

[GitHub](https://github.com) is an online platform for hosting Git repositories. It makes it easy to store your projects in the cloud, track changes across different computers, and later on collaborate with others.  

For now, our focus is on **setting up and using GitHub for ourselves**. We'll practice creating repositories, pushing changes, and managing branches remotely, for ourselves to begin with, before introducing collaboration with others.  

Now, make sure you have a [GitHub account](https://github.com/signup) before you continue.  

## Two ways to connect with GitHub

There are two common ways to create and use a remote repository:  

- **Clone from GitHub**: Start with a repository that already exists on GitHub and "clone it" (bring it down) to your computer.  
- **Push to GitHub**: Start with a repository on your computer and then "push" (upload) it to GitHub.

We'll practice both.

## Cloning a repository from GitHub

1. On GitHub, create a new repository.  
   - When creating it, you can choose to add a README file so the repo isn't empty. **Do this!**  

2. After creation, click the green **Code** button and copy the HTTPS URL, referred to as `<repository-url>` going forward.  
   - The first time you push or pull from GitHub, you may be asked to authenticate. This usually means signing in with your GitHub account or providing a personal access token (instead of a password).  

3. On your computer, clone the repository and move into its folder:  
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ````

4. Verify that the repository was cloned successfully:
   ```bash
   git status
   ```

   You should see something like:
   ```
   On branch main
   Your branch is up to date with 'origin/main'.

   nothing to commit, working tree clean
   ```

   This means you are on the `main` branch and it is already linked to the remote copy (`origin/main`) on GitHub.

5. To double-check the remote connection, run:
   ```bash
   git remote -v
   ```

   You should see two lines showing your `<repository-url>` for both **fetch** and **push**, for example:
   ```
   origin <repository-url> (fetch)
   origin <repository-url> (push)
   ```

At this point, you have a local copy of the repository, already connected to GitHub. Any commits you make can be sent back with `git push`.

**TODO - working on it!**
