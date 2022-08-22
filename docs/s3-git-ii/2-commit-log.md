---
layout: default
title: Commit Log
nav_order: 2
parent: Git II
---

# Looking at the commit log

Once you have made multiple commits, you can see these commits, their dates, commit messages, author, etc. by typing `git log`. This command will open a scrollable interface (using the up/down arrow keys) that you can get out of by pressing the `q` key. As we saw earlier, you can also see the history of commits through on GitHub’s web interface, but it is also useful to be able to access the commit log directly from the terminal, without having to open a browser.

Run the command `git log` from either the repository in your home directory (`/home/USER/capp30121/camp-1-GITHUB-USERNAME`) or in the temp directory (`/tmp/USER/capp30121/camp-1-GITHUB_USERNAME`). You should see output that looks something like this

```
commit 7abeffd2ba2a00ed697b25d90af18bd803d44588 (HEAD -> main, origin/main, origin/HEAD)
Author: GITHUB_USER <GITHUB_EMAIL>
Date:   Fri Aug 5 08:26:46 2022 -0500

    update test.txt

commit 19a476da446d473adf91838bedfcd44f21f4fcbe
Author: GITHUB_USER <GITHUB_EMAIL>
Date:   Mon Aug 1 10:53:58 2022 -0500

    final changes to favorite-things.txt

commit 094b3e89238ae2b9383b26e08e4b90150b95ce08
Author: GITHUB_USER <GITHUB_EMAIL>
Date:   Mon Aug 1 10:47:20 2022 -0500

    add favorite-things.txt
```

Each commit has a _commit hash_ (usually referred to as the _commit SHA_) that looks something like this:

```
7abeffd2ba2a00ed697b25d90af18bd803d44588
```

This is a unique identifier that we can use to refer to that commit elsewhere. For example, choose any commit from the commit log and run the following:

```
git show COMMIT_SHA
```

Make sure to replace `COMMIT_SHA` with a commit SHA that appears in your commit log.

This will show you the changes that were included in that commit. The output of `git show` can be a bit hard to parse at first but the most important thing to take into account is that any line starting with a `+` denotes a line that was added, and any line starting with a `-` denotes a line that was removed. (Recall that this is the same formatting we saw when [using `git diff`](../s2-git-i/5-discarding-changes-unstaging.html) to show the pending changes to a file in the first Git lab.)

{: .tip}
> In any place where you have to refer to a commit SHA, you can just write the first few characters of the commit SHA. For example, for commit `9119c6ffcebc2e3540d587180236aaf1222ee63c` we could write just this:
>
> ```
> git show 9119c6f
> ```
> Git will only complain if there is more than one commit that starts with that same prefix.

{:style="text-align:center"}
[Previous](./1-working-from-multiple-locations.html){: .btn } [Next](./3-merge-conflicts.html){: .btn }
