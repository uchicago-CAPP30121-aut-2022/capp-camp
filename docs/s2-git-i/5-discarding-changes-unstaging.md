---
layout: default
title: Discarding Changes and Unstaging
nav_order: 5
parent: Git I
---

## Discarding changes and unstaging

One of the benefits of using a version control system is that it is very easy to inspect the history of changes to a given file, as well as to undo changes we did not intend to make. For example, edit `test.txt` to remove all its contents. `git status` will tell us this:

    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   test.txt
          
    no changes added to commit (use "git add" and/or "git commit -a")

If we want to see what we have changed in the `test.txt` file since our last commit, we can use `git diff` to output the changes to the terminal. Run `git diff test.txt`. You should see something like this:

    diff --git a/test.txt b/test.txt
    index bf87536..e69de29 100644
    --- a/test.txt
    +++ b/test.txt
    @@ -1,3 +0,0 @@
    -Hello, World!
    -
    -Git is pretty cool.
    \ No newline at end of file

Lines that begin with `-` indicate content that has been removed from `test.txt`, while lines that begin with `+` indicate content that has been added to `test.txt`. We only deleted lines from the file, so there should be no lines beginning with `+` in the output.

> **VSCode Tip**
> 
> To view the changes that you have made to `test.txt` in the VSCode window, you can click on the Source Code icon and then click on the file in the dropdown. VSCode will display in a new file tab two versions of the file, the previous version last committed and the new version with color-coded highlights to identify modifications.

If we want to discard the changes we made to `test.txt`, all we have to do is follow the helpful advice provided by the above output:

    git restore test.txt

> **Note**
> 
> In older versions of Git, `git status` may refer to the `git checkout` command. In that case, run this command instead:
> 
> `git checkout -- test.txt`

If you open `test.txt`, you’ll see that its contents have been magically restored!

Now, edit `test.txt` and `README.md` to add an additional line with the text `Hopefully our last change...`. Run `git add -u` but don’t commit it just yet. `git status` will show this:

    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            modified:   README.md
            modified:   test.txt

Now, let’s say we realized we want to commit the changes to `README.md`, but not to `test.txt`. However, we’ve already told git that we want to include `test.txt` in the commit. Fortunately, we can “un-include” it (or “unstage” it, in Git lingo) by running this:

    git restore --staged test.txt

> **Note**
> 
> In older versions of Git, `git status` may refer to the `git reset` command. In that case, run this command instead:
> 
> `git reset HEAD test.txt`

Now, `git status` will show the following:

    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            modified:   README.md
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   test.txt

Go ahead and run `git commit -m "Update README.md"`. The commit will now include only `README.md`.

Before moving on to the exercises of the lab, let’s make sure all our changes have been committed and pushed:

    git add -u
    git commit -m "Wrapping up guided part of the lab"
    git push

Before continuing, make sure `git status` shows this:

    On branch main
    Your branch is up to date with 'origin/main'.
    
    nothing to commit, working tree clean
