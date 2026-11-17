# Final Project


- [Task list:](#task-list)
- [Make a one-page website of your
  project](#make-a-one-page-website-of-your-project)

This repository is for the delivery of your final data science project.
See the course Website for details how that project should look. Also
notice the feedback you got after your project check-in. You have
learned the basic workflow of writing and coding using a quarto markdown
(`.qmd`), rendering static HTML files and commiting and pushing your
work to GitHub in former Homework projects.

Regularly, you will do your final project in a **team** of students.
**Collaborative Data Science** is also a learning goal, conceptually and
technically using git and GitHub.

## Task list:

- [ ] Do the [GIT_COLLABORATION_EXERCISE](GIT_COLLABORATION_EXERCISE.md)
  with your whole team first.
- [ ] Discuss together who is working on what and what parts you need to
  coordinate.
- [ ] Do the data science work. There are 2 options:
  - Start collaboratively on `report.qmd` together and coordinate who
    works on what and what languages you use. Coordination should help
    that you do not run into merge conflicts too often.
  - Alternatively, each team member creates a file `report_NAME.qmd` for
    the initial work. That way team members can work more independently,
    but you need to do coordination work later to put everything into
    `report.qmd`.
- [ ] Check if script files are needed, for example to retrieve data or
  make computation heavy analyzes which should not be executed every
  time you render `report.html`.

Delivery:

- [ ] If you have started with independent files, put your work together
  in `report.qmd`
- [ ] Render `report.html` and scrutinize that it looks good. This is
  the main file for the assessments.
- [ ] Make “Final Commit” and include: `report.qmd`, `report.html`, all
  other files needed to reproduce the analysis. For the data files there
  are some exceptions when they are large or confidential. In case you
  can or do not want to upload all data, provide a script how data could
  be retreived, or (as a minimal requirement) provide a documentation
  `Data_Retrieval` in written form (for example in `.md`, `.txt` format)
  which explains how data can be retrieved to reproduce the analysis.
- [ ] Push this commit to GitHub and make the following test:
  - [ ] Go to the GitHub page and clone your repository anew to a new
    place (for example to your Download folder).
  - [ ] Go to the folder and open the local HTML file in your browser.
    That way you repeat what instructuros will do. You are done, when it
    looks as expected.
  - [ ] You can delete the new version. It was just to double-check if
    everything needed is in.
- [ ] Discuss in your team if you would like to have your project
  repository public. If yes, write a message to the instructor with this
  request. You can receive admin rights for your repository. Then you
  can make it public yourself. You can then also produce a one-page
  Website for it with GitHub Pages.

## Make a one-page website of your project

Your report can be published with GitHub Pages. This is a nicely way to
show it to the outside world. The are three different ways of [Quarto
Publishing with GitHub
Pages](https://quarto.org/docs/publishing/github-pages.html).

Here are the steps you need to do:

- [ ] Get **admin** rights for your repository from your instructor
  (then you have access to the *Settings* tab your remote repository in
  the browser)
- [ ] Make you private repository **public** (scroll down to the *Danger
  Zone*)
- [ ] Enable **GitHub Pages** in your repository settings: On subpage
  *Pages* select Branch *main* and folder */ (root)*.
- [ ] Rename `report.html` to **`index.html`**. `index.html` is a
  standart name for websites. You a server is asked for web-content from
  a folder (here */ (root)* of your repository) it delivers
  `index.html`.
- [ ] After some time GitHub should show you a link in the domain
  `github.io` where your one-page website lives on the *Pages* subpage.
