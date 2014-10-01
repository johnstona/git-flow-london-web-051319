---
languages: bash, git
tags: git, merge, pull, fetch, commit, pull, push, wip
resources: 5
---

# Git Flow

## Objectives

* Get familiar with git syntax
* Get comfortable creating, merging, pushing, and pulling branches.
* Resolve merge conflicts

## Instructions

Remember to fork and clone this lab if you haven't already.

### Branching

Before altering your code base, open `index.html` in the browser. In the first part of this lab, you're going to add a photo of a turtle below the image of the tree.

* Type `git branch`. This should return master.
* Make a new branch called `add-turtle` from the master branch: `git branch add-turtle`
* Type `git branch` again. Now you should see `master` (highlighted) and `add-turtle` 
* Switch to the turtle branch: `git checkout add-turtle`
* Make sure you switched successfully by typing `git branch` again. This should return `master` and `add-turtle` (highlighted).
* In `index.html`, below the tree picture and caption section, add the turtle picture using the HTML below:

```HTML
<!-- begin turtle picture and caption -->
<div class="center-container">
  <div class="card">
    <div class="caption">
      <h4>From the Sky</h4>
      <p>Montse Grillo</p>
      <p>Tenerife, Canary Islands</p>
    </div>
  </div>
  <div class="card">
    <img src="public/img/turtle.jpg" alt="sea turtle swimming">
  </div>
</div>
<!-- end turtle picture and caption -->
```
* Open up your `index.html` and see how the page looks.
* Stage and commit your changes.

### Merging

Now that you've sucessfully added a turtle pic and caption to the add-turtle branch, you're going to merge that branch into master.

* The first step is to switch back to the master branch: `git checkout master`
* Now you're going to merge the add-turtle branch in: `git merge add-turtle`
* Open up your `index.html` in the browser. How does it look? Does it have two pictures now? 

While you have this change locally, your remote repo still thinks that `index.html` just has one picture, the tree/bird one. You need to tell about this update.
* Push the update to your master branch on your remote repo: `git push origin master`
* To make sure this push worked, visit your fork of this repo. From there, you can double check in at least two ways: 
  1. There will be a light blue bar above the file struture of the repo:
  ![blue bar](/img/blue-bar.png) that displays the most recent commit. This bar should have your GitHub picture followed by your GitHub name and a time stamp.
  2. Click on ![num of commits](/img/commits.png). The most recent commit, the one at the top, should be the one you made.

* Let's get local again: How many branches do you expect to see when you type `git branch`? How many are there? What does this tell you about merging?

### Deleting A Local Branch

Now that you've added the changes you've made from add-turtle to master, and master has been pushed to the remote repo successfully, it's time to delete your local version of add-turtle.

* Make sure you're on master: `git branch` should return `master` highlighted.
* Type `git branch -d add-turtle`
* To make sure this branch was sucessfully deleted, type `git branch`. You should only see `master` now.


## Resources
* [SourceTree Blog](http://blog.sourcetreeapp.com/) - [Merge or Rebase?](http://blog.sourcetreeapp.com/2012/08/21/merge-or-rebase/)
* [Pro Git](http://git-scm.com/book/) - [Chapter 3 Git Branching](http://git-scm.com/book/en/Git-Branching)
* [Pro Git](http://git-scm.com/book/) - [3.1 Git Branching - What a Branch Is](http://git-scm.com/book/en/Git-Branching-What-a-Branch-Is)
* [Pro Git](http://git-scm.com/book/) - [3.2 Git Branching - Basic Branching and Merging](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)
* [LearnGitBranching](http://pcottle.github.io/learnGitBranching/) - [Introduction Sequence: Branching in Git](http://pcottle.github.io/learnGitBranching/)