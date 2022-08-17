---
layout: default
title: Git II
nav_order: 5
has_children: true
---

# Git Part II: Working Collaboratively

So far, we have used Git to work solo on a project from a local repository in a single location. While Git is certainly useful for working in this manner, it would probably not be the version control system of choice for many professional software teams if that was all it was good for. What makes Git so powerful and valuable is that a Git repository can exist in multiple locations and enable an entire _team_ to work on a GitHub repository simultaneously, all while tracking the changes in each copy of a repository and seamlessly merging the work from all of them. When you work on a project with others, Git's functionality allows you to divide and conquer, so that each member of a team can make contributions to the code while continuing to incorporate each other's work.

In this lab, we will explore some important features of Git that enable this collaborative work, including how to clone a Git repository so that you can work on it from multiple locations, the kinds of issues that might arise when working from multiple locations and how to resolve them, and useful commands to monitor the history and state of a Git repository.

## Objectives

1. Become comfortable with cloning an existing repository using `git clone`

2. Understand what a merge conflict is and how to resolve it

3. Learn commands to visualize the history of commits to a repository using `git log`

4. Sync a local repository with an upstream (remote) repository and incorporate changes added to the remote repository

## Where should you do this lab?

You can work on this lab on your own computer from anywhere, but you will need to have access to the Linux servers hosted by the CS department at UChicago. This lab is meant to be completed on these servers, so you will need to connect to a server using your CS account and SSH key (which you should have done in the first lab of CAPP Camp) before starting. Please connect to your assigned Linux server now through VSCode and open a terminal in VSCode. Let either the instructor or the TA know if you need assistance connecting.

## Acknowledgments

Many CS 121 instructors and TAs have worked on this lab over the years. Gustav Larsson (PhD ‘17) and Isha Mehrotra (SB’19) deserve special mention. Gustav wrote the original version of this lab and Isha wrote the original material on merge conflicts.
