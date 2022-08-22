---
layout: default
title: Exercises
nav_order: 5
parent: Git II
---

## Exercises

 1. As we did at the start of this lab, clone the repository `camp-2-GITHUB_USERNAME` in the `/tmp/USER/capp30121` directory that you have been working with throughout this lab. Be sure to use the SSH URL (beginning with `git@github.com:...`) to clone this repository.
 
 2. Generate a merge conflict in the `camp-2-GITHUB_USERNAME` repository. Edit `hello.py` in the home repository by changing `World!` to your name:
    
    ```
    print("Hello, YOUR_NAME!")
    ```

    Commit and push the new version of `hello.py` to the server. Pull the change to your temp repository. Now, in your temp repository, edit `hello.py` again to change `YOUR_NAME!` to `CAPP 30121!`:
    
    ```
    print("Hello, CAPP 30121!")
    ```

    Commit and push the changes to the GitHub server.
    
    Switch back to your home repository. Do **not** run `git pull` just yet. Edit `hello.py`, replacing `CAPP 30121!` with `universe!`. Attempt to add, commit, and push the change to the server. Did the attempt to push the commit work? Run `git pull`.

    Oh no! Looks like we have another merge conflict. Using the steps that we followed in this lab, resolve the merge conflict, keeping the changes that you added from the temp repository. Be sure that both the home directory and the temp directory contain the same version of `hello.py` once you have fixed the merge conflict. **Hint**: `hello.py` should contain the following line at the end of this exercise:
    
    ```
    print("Hello, CAPP 30121!")
    ```

 3. Use `git log` to find the commit SHA of the _merge commit_ that you created to resolve the merge conflict from exercise 2. Use `git show` to view the changes in that commit. Pipe the output from `git show` into a new file called `changes.txt`. Commit the new file and push to GitHub.

{:style="text-align:center"}
[Next Lab](../s4-python/index.html){: .btn }
