---
layout: default
title: Exercises
nav_order: 6
parent: Git I
---

# Exercises

 1. In the `test.txt` file, add a new line with the text `Definitely the last change!`. Add and create a commit with the change to `test.txt` with the commit message `final changes to test.txt` and push to GitHub. Check the GitHub website to ensure that your changes appear there.

 2. Create a new file in your `camp-1-GITHUB-USERNAME` directory called `favorite-things.txt`. Add text to this file to list a few of your favorite things (three is enough). Now, add an additional line of text to the `README.md` that says `Definitely the last change!`. Commit *only* the changes that you made to `README.md`. Use `git commit` without the `-m` flag and use the text editor that Git opens for you to add a multi-line commit message that says:

    ```    
    final changes to README.md
    Some more comments on an additional line
    ```
 
    Use `git status` to confirm that you have added only the changes to `README.md` before pushing the commit to GitHub. Check the GitHub website to see if you completed this excercise correctly. *Hint*: You should **not** see the new file that you created (`favorite-things.txt`) on GitHub.

 3. Add the new file `favorite-things.txt` to a commit and push the file to GitHub. After confirming that the new file appears on GitHub, edit the file to add an additional line of text to include something that you dislike.

    Use Git to restore `favorite-things.txt` to include only your favorite things. Use `git status` to confirm that you have not made any new changes to `favorite-things.txt` since your last commit. *Hint*: You should **not** need to edit `favorite-things.txt` in VSCode to restore the original text.

 4. Add your full name and CnetID to the top of `favorite-things.txt`. Add these changes to a new commit but **do not** commit and push them just yet. After staging this last change to a commit, you realize that you forgot to include an additional update to `favorite-things.txt`.
 
    Unstage `favorite-things.txt`, add one more favorite thing to the list in the file, and then commit and push your changes to the remote repository. Use `git status` to confirm that there are no pending changes in your repository. Check GitHub to make sure that `favorite-things.txt` includes all of your recent changes.

{:style="text-align:center"}
[Next Lab](../s3-git-ii/index.html){: .btn }
