---
layout: default
title: Git I
nav_order: 4
has_children: true
---

# Git Part I: Introduction to Git

Git is a system used for developing software in a group. In a nutshell, Git is a _version control system_ that maintains files in a _repository_ that contains not just files, but also a record of all the changes made to those files. Git tracks every version of a file or directory using _commits_. When you have made changes to one or more files, you can logically group those changes into a “commit” that gets added to your repository. You can think of commits as “checkpoints” in your work, representing the work you’ve done since the previous checkpoint. This mechanism makes it possible to look at and even revert to older versions of a file by going back to your code as it was when you “checkpointed” it with a commit.

You will each have a set of personal Git _repositories_, one per assignment, that will be hosted on a central server.

This lab provides a tutorial-style introduction to various aspects of Git. All you need to do is follow the instructions and complete the exercises at the end of the lab to practice the covered concepts. Please do make sure you understand what is accomplished in each step and, if you have any questions, please don’t hesitate to ask for help.

## Objectives

1. Become familiar with the basic concept of Git and why it is useful

2. Set up a GitHub account and create an SSH key to connect to GitHub from a terminal

3. Initiatlize a Git repository

4. Become comfortable with the Git workflow and using `git add` and `git commit`

5. Understand how to sync your local work with a remote server through `git push`

## Where should you do this lab?

You can work on this lab on your own computer from anywhere with an internet connection, but you will need to have access to the Linux servers hosted by the CS department at UChicago. This lab is meant to be completed on these servers, so you will need to connect to a server using your CS account and SSH key (which you should have done in the first lab of CAPP Camp) before starting. Please connect to your assigned Linux server now through VSCode and open a terminal in VSCode. Let either the instructor or the TA know if you need assistance connecting.

To open a new terminal in VSCode, select “Terminal > New Terminal” on the Menu Bar. The terminal that appears will use the default shell (i.e., bash for Linux). You can see the terminal listed according to its shell name on the righthand side of the terminal panel.

## Acknowledgments

Many CS 121 instructors and TAs have worked on this lab over the years. Gustav Larsson (PhD ‘17) and Isha Mehrotra (SB’19) deserve special mention. Gustav wrote the original version of this lab and Isha wrote the original material on merge conflicts. This lab has been updated by Marc Richardson (MSCAPP '19) and Launa Greer (MSCAPP '19).

{:style="text-align:center"}
[Start the Lab](./1-getting-started.html){: .btn }
