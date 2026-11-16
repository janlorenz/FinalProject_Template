# Collaborative Git Exercise


- [Purpose](#purpose)
- [In a nutshell](#in-a-nutshell)
- [Step 1: git clone this
  repository.](#step-1-git-clone-this-repository)
- [Step 2: A commits and pushes](#step-2-a-commits-and-pushes)
- [Step 3: B pulls](#step-3-b-pulls)
- [Step 4: Merge independent changes](#step-4-merge-independent-changes)
- [??? `git` configuration for divergent
  branches](#-git-configuration-for-divergent-branches)
- [Step 5: Push and pull the other way
  round](#step-5-push-and-pull-the-other-way-round)
- [Step 6: Create a merge conflict](#step-6-create-a-merge-conflict)
- [Step 7: Solve the conflict](#step-7-solve-the-conflict)
- [Advice: Collaborative work with
  git](#advice-collaborative-work-with-git)
- [Background and Outlook](#background-and-outlook)

## Purpose

- **This is a team exercise!**
- It should take about 15 minutes.
- You do this together.
- You can be in one room, or in an online work session. You should be
  able to look at each others screens (by peeking or screen sharing).

**Learning goal:** Collaborative data science work with `git` over
GitHub. The **pull-push cycle**. Solving git-conflicts.

You practice this basic git workflow when there are more than one
contributors:

![A basic git workflow represented as two islands, one with “local repo”
and “working directory”, and another with “remote repo.” Bunnies move
file boxes from the working directory to the staging area, then with
Commit move them to the local repo. Bunnies in rowboats move changes
from the local repo to the remote repo (labeled “PUSH”) and from the
remote repo to the working directory (labeled
“PULL”).](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/68739659-fb6f-41e8-9813-32e1de3d82c0_rw_3840.png?h=5c36d3c50c350a440567a1f8f72ac028)
Source Drawings: Allison Horst https://allisonhorst.com/git-github

## In a nutshell

- The new workflow for a work session is: git **pull** - *Work* - git
  add - git commit - git push  
  Before you start working you **pull** to get the works of others. That
  is the new part compared to the individual workflow.
- But maybe you have worked already on your files locally, so trying to
  pull the work of others results in an error because git will not
  overwrite your local changes. What to do?
- You do a commit of your work (or remove it if it is not worth to
  keep). Then you pull again.
- git will try to **merge** your local commit with the commit in the
  remote repository.
  - When the work of others is on a different part that you did not
    change, then git puts this parts in your file and you magically have
    a version with both parts updated: yours and the other.
  - When the two commits have changes that overlap, you encounter a git
    conflict which git marks in the document and you have to resolve the
    conflict manually.

You will practice that in the exercise.

**Conclusion for collabortive work over git**

- You do net need to plan exactly who touch files when. You can work in
  parallel on your local copies. Different versions of files can be
  merged.
- Planing who is working on what and when can however minimize the need
  to solve merge conflicts.

Now to the exercise. Follow these steps in your project team.

Assign roles of team member A, B, C, … (There will be different tasks
mostly for A and B)

## Step 1: git clone this repository.

All team members do the following:

- Copy the URL  
- Go to Positron
  - New Folder from Git… \> Paste your URL
  - The project is created at the place you select

## Step 2: A commits and pushes

**Team member A:**

- Open the file `report.qmd`
- Write your name in the first line at `author` in the YAML
- `git add` the file `report.qmd`
- `git commit` (enter “Added name” as commit message)
- `git push`

## Step 3: B pulls

**Team member B:**

- Do `git pull`, or find the button “Pull” in the GRAPH section of the
  Source Control Tab of Positron.

**What does `git pull` do?**

- `git pull` does two things: fetching new stuff and merging it with
  existing stuff
  1.  First, it `git fetch`es the commit from the remote repository
      (GitHub) to the local machine
  2.  Then, it `git merge`s the commit with the latest commit on your
      local machine.
- When we are lucky merging works with no problems.

![Illustration highlighting the difference between git fetch and git
pull. On the left (representing git fetch), a crocodile holding a box
says to another crocodile eating salad: “They had a new topping mix at
the store. Check it out, it might be good in your salad.” On the right
(representing git pull), a crocodile says “They had a new topping mix at
the store. I bought some and mixed it into your salad” while a concerned
looking crocodile looks at their salad, which now contains the topping
mix of insects. Text at the bottom reads “Check what you’re getting
before merging it in with git
fetch.”](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/7f2a398a-3351-49e4-8430-5d1793c5a775_rw_3840.png?h=0cdf228a877ef47a90b0eb97e1d8a8f3)

## Step 4: Merge independent changes

Git can merge changes in the same file when there are no conflicts.
Let’s try.

- **Team member B:**
  - Add your name in the author section of the YAML, save the file,
    `git add`, `commit` and with message “Next author name” and `push`.
- **Team member C (or A again):**
  - Change the title in the YAML to your title and also add your name
    (if you are the third team member not the first again), save the
    file, `git add` and `commit` with message “Title changed”.
  - Try to `push`. You should receive an error. Read it carefully, it
    may tell you what to do. Here: Do `git pull` first. Why you can’t
    push? Because remotely there is a newer commit (the one B just
    made).
  - `Pull`. This should result in message about a **successfull
    auto-merge**. Check that **both** are there: Your line and the line
    of your colleague. *If you receive several hints instead, first read
    the next section!*

## ??? `git` configuration for divergent branches

If you pull for the first time in a local git repository, git may
complain like this:

<img
src="https://raw.githubusercontent.com/CU-F26-MDSSB-01-Concepts-Tools/Website/refs/heads/main/lectures/img/gitconfigrebase_rstudio.png"
height="200" />

Read that carefully. It advises to configure with
`git config pull.rebase false` as the default version.

**How to do the configuration?**

- Copy the line `git config pull.rebase false`.
- Go to the TERMINAL. Paste the command (Ctrl+Shift+V) and press enter.
  Now you are done and `git pull` should work.

What is a *branch* and what a *rebase*? These are features of git well
worth to learn but not now. Learn at <http://happygitwithr.com>

## Step 5: Push and pull the other way round

- **Member C (or A):**
  - The successful merge creates a new commit, which you can directly
    push.
  - `push`
- **Member B (and all others):**
  - `pull` the changes of your colleague.

Practice a bit more pulling and pushing commits and check the merging.

## Step 6: Create a merge conflict

**Members A and B:**

- Write a different sentence after “Executive Summary.” in YAML
  `abstract:`.
- Both `git add` and `git commit` on their local machines.

**Members A:** `git push`

**Member B:**

- `git pull`. That should result in a conflict. *If you receive several
  hints instead, first read the section “???” above*
- The conflict is visible directly in the file with markings like this

`>>>>>>>>`  
one option of text,  
`========` a separator,  
the other option, and  
`<<<<<<<`.

## Step 7: Solve the conflict

**Member B**

- You have to solve this conflict now!
- Solving is by editing the text
- Decide for an option or make a new text
- Thereby, remove the `>>>>>`,`=====`,`<<<<<<`
- When you are done: `git add`, `git commit`, and `git push`.

Now you know how to solve merge conflicts. Practice a bit in your team.

## Advice: Collaborative work with git

- First **pull** whenever you start a work session in a collaborative
  project.
- Inform your colleagues when you pushed new commits.
- Coordinate the work, e.g. discuss who works on what part and maybe
  when.
- When you finish your work session, end with pushing a *nice* commit.
  Nice means: The file should preview well.
- When you work on different parts of the file, be aware that also a
  successful merge can create problems. Example: Your colleague changed
  the data import, while you worked on graphics. Maybe after the merge
  the imported data is not what you need for your cell.
- In your project coordinate your data import and wrangling!
- Commit and push often. This avoids that potential merge conflicts
  become large.

## Background and Outlook

Two more illustrations of [Allison
Horst](https://allisonhorst.com/git-github)

![](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/33f12eb3-e65b-46df-9a2e-e4b24a4b59cd_rw_3840.png?h=6f05681451d60f6ba15ae8f7cef56ba2)

![](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/7a5f458a-3d63-4e46-8a09-c417e52587ea.png?h=488d2d9a4159f82cdf851a70182e52e6)

A more advanced github workflow also includes branches and pull
requests. Here you get a first idea. You may create a branch to test a
new version while the `main` version should stay in place. In larger
projects, not everyone working with a local version of a repo has push
access, but when someone wants to propose a new better version to the
project maintainers (who have push access) they can make a pull request.
The maintainer then checks it and pulls it into the `main` branch.

![](https://cdn.myportfolio.com/45214904-6a61-4e23-98d6-b140f8654a40/efae32ce-863f-4773-852c-4335e3ce4709_rw_3840.png?h=c54a2e5af240ec6e1332e2dcacbd7f33)
