# Software Lifecycle Management
## Final Project
## Java Game TicTacToe

by Eva Lehner, Florian Scholz, Sophie Schönwälder-Rieder
February, 2026







# Table of Contents
- [[#000 - Welcome|000 - Welcome]]
- [[#001 - Create a GitHub repository (public)|001 - Create a GitHub repository (public)]]
- [[#002 - Create a GitHub project and link it to the created repository|002 - Create a GitHub project and link it to the created repository]]
- [[#003 - Transfer the user stories to a new Kanban board in the project|003 - Transfer the user stories to a new Kanban board in the project]]
- [[#004 - Add additional issues to the kanban board|004 - Add additional issues to the kanban board]]
- [[#005 - Create a new Java Maven project|005 - Create a new Java Maven project]]
- [[#006 - Set the GitHub repository as a remote repository|006 - Set the GitHub repository as a remote repository]]
- [[#007 - Commit and push your blank Java project to the main branch|007 - Commit and push your blank Java project to the main branch]]
- [[#008 - Protect the main branch|008 - Protect the main branch]]
- [[#009 - CI_CD Scripts and workflows|009 - CI_CD Scripts and workflows]]
- [[#010 - Working on User Stories|010 - Working on User Stories]]
- [[#011 - A final overview|011 - A final overview]]


<div style="page-break-after: always;"></div>


## 000 - Welcome
This document serves as documentation for the SLM-project 'Java Game TicTacToe' and provides a walkthrough illustrating the most important steps of our development process with short textual description as well as screenshots - focussing on our usage of GitHub and application of concepts studied in the seminar rather than on the game itself.

The structure of the documentation follows the chronology of our workflow - which in turn closely followed the list of tasks provided in the task description.

Regarding our collaborative process: Especially in the earlier stages of the project, the majority of tasks were done together, triple programming style. The intent was to maximise knowledge gain for all team members. 

*This is mentioned here to prevent faulty impressions that might be caused by the statistics showing that one member of the team authored significantly more commits than the other two members in the beginning. This is due to the fact that their account was typically used for the tasks we tackled together, mainly to simplify the workflow and keep the screenshots similar.*

The GitHub repository can be accessed at https://github.com/ww24e018/slm-tictactoe
The project (Kanban Board) can be accessed at https://github.com/users/ww24e018/projects/1
The .jar of our latest release of the game can be downloaded at https://github.com/ww24e018/slm-tictactoe/releases

In the process of exploring workflows and ci/cd, a test repository was created to provide a playground for quick trials that require changes to be present on the main branch. This repo can be accessed here, should it be of any interest: https://github.com/ww24e018/slm-tictactoe-test

**Contributors**: Eva Lehner, Florian Scholz, Sophie Schönwälder-Rieder



<div style="page-break-after: always;"></div>



## 001 - Create a GitHub repository (public)

At https://github.com/repos a new repository was created by clicking "new repository":

![[Pasted image 20260203093006.png|400]]
The name "slm-tictactoe" was chosen.
![[Pasted image 20260203093113.png|400]]
The repository was successfully created.
![[Pasted image 20260203093136.png|400]]
In order to successfully collaborate in this new repository, the other team members were invited as collaborators:
 Go to "Settings":
 ![[Pasted image 20260203101710.png|400]]
Go to "Collaborators":
![[Pasted image 20260203101732.png|200]]


![[Pasted image 20260203101747.png|400]]



![[Pasted image 20260203101802.png|400]]


![[Pasted image 20260203101857.png|200]]



<div style="page-break-after: always;"></div>


## 002 - Create a GitHub project and link it to the created repository

A new project was created by choosing the tab "Projects":
![[Pasted image 20260203093307.png|400]]
![[Pasted image 20260203093415.png|400]]
After clicking "+ New project":
![[Pasted image 20260203093443.png|400]]

Choosing "Kanban":
![[Pasted image 20260203093518.png|400]]
Naming new project and linking it to our existing repository:
![[Pasted image 20260203093630.png|400]]

Hooray! We have a blank kanban board!
![[Pasted image 20260203093648.png|400]]

after reload:
![[Pasted image 20260203093705.png|400]]
At first we assumed that rights to the repo automatically give rights to the project linked to it. After realising that this was not the case, all team members were invited to the project as well:
![[Pasted image 20260203114328.png|400]]
clicking Settings:
![[Pasted image 20260203114425.png|400]]
Clicking "Manage access":
![[Pasted image 20260203114451.png|400]]
Inviting via "Invite" via the process followed.


<div style="page-break-after: always;"></div>

## 003 - Transfer the user stories to a new Kanban board in the project

The user stories in the project description are:
- As a player, I want to be able to **make a move** by choosing an empty square, so that I can place my symbol on the board. (1)
- As a player, I want to be able to **see the current state** of the game, so that I can keep track of the moves made by both myself and my opponent.  (2)
- As a player, I want to **be notified when the game has ended** in a win, loss or draw, so that I can see the result of the game.  (3)
- As a player, I want to be able to **start a new game** after the current game has ended, so that I can play again. (4)

The bold parts will be chosen as titles. The parts in () are the Ids given by us.

The Board:
![[Pasted image 20260203094352.png|400]]
Clicking "add item" in the backlog-column:
![[Pasted image 20260203094420.png|200]]

Clicking "+" is possible:
![[Pasted image 20260203094444.png|200]]


![[Pasted image 20260203094454.png]]


`create new issue` 
![[Pasted image 20260203094516.png|400]]

Filling in title and description:
![[Pasted image 20260203094656.png|400]]
The first issue has been created:
![[Pasted image 20260203094822.png|400]]
Screenshots of 2 and 4 and the final state:
![[Pasted image 20260203094903.png|400]]

![[Pasted image 20260203095116.png|400]]

The board:
![[Pasted image 20260203095148.png|400]]




<div style="page-break-after: always;"></div>


## 004 - Add additional issues to the kanban board

Additional issues were created to enable branch-naming for setup-tasks.
It was discovered there is a default WIP-Limit for the backlog column. It was at first randomly changed to 50 and later cleared altogether as we did not feel a necessity for a WIP limit in the backlog section in the context of this project.

![[Pasted image 20260203115310.png|200]]

The following items were added:
![[Pasted image 20260203115457.png|400]]

![[Pasted image 20260203115512.png|400]]
Issue #6 was further divided into 3 subissues:
![[Pasted image 20260210154438.png|400]]

Additionally, a couple of new issues were created regarding workflows and ci/cd, in order to set everything up correctly before starting to work on the actual user stories.


<div style="page-break-after: always;"></div>


## 005 - Create a new Java Maven project

A new Java Maven project was created in the IDE and a new git repository was initialised in the process.

![[Bildschirmfoto von 2026-02-03 10-11-53.png|400]] 


<div style="page-break-after: always;"></div>

## 006 - Set the GitHub repository as a remote repository

![[Bildschirmfoto von 2026-02-03 10-21-35.png|400]]



<div style="page-break-after: always;"></div>

## 007 - Commit and push your blank Java project to the main branch

On our initial push to the main branch, we had a conflict between our local and remote branches. 
Following differences lead to this: 
1) Remote branch was named `main` and local branch `master`. 
2) On creation of the repository in github we added a .gitignore which was different to the .gitignore file that was automatically generated by IntelliJ. 

We resolved this by (see screenshot of history)
1) Rename master (local) to main (`git branch -m master main`)
2) Pull (`git pull git@github.com:ww24e018/slm-tictactoe.git main`)
3) Set upstream of local main to origin/main (`git branch --set-upstream-to=origin/main`)
4) Git push 
5) Rebase & resolve conflict 
6) git push 

![[Bildschirmfoto von 2026-02-03 10-29-11.png|400]]


![[Bildschirmfoto von 2026-02-03 10-45-48 1.png|400]]


History leading to rebase button: 

![[Bildschirmfoto von 2026-02-03 10-51-21.png]]

![[Bildschirmfoto von 2026-02-03 10-52-15.png]]

---

Screenshot of the commit history on GitHub:
![[Pasted image 20260203111530.png|400]]


<div style="page-break-after: always;"></div>

## 008 - Protect the main branch

![[Pasted image 20260203111854.png|400]]
After reading documention about branch protection rules ([repository rules](https://docs.github.com/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets) /
[protected branches](https://docs.github.com/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)), it was decided to try the "add classic button":
![[Pasted image 20260203112504.png|400]]

![[Pasted image 20260203112529.png|400]]

Defaults appearing after clicking the first checkbox
![[Pasted image 20260203112755.png|400]]

Other options were left at default.
After clicking 'create':
![[Pasted image 20260203112959.png|400]]



<div style="page-break-after: always;"></div>

## 009 - CI_CD Scripts and workflows

### The process of research and development

To simplify research and development - and to keep the submission repo free of commits doing trial and error on syntax and meaning - a decision was made to use a custom test-repository on GitHub to experiment more freely.

This repository is also public and is available [here](https://github.com/ww24e018/slm-tictactoe-test) if a deeper view into that process is required (or desired). 

It does not have the full spectrum of main-branch protections because its purpose is to serve as a playground for quick test runs that might require changes to be present on main.

![[Pasted image 20260209103218.png|400]]

### The process of implementing results

was the usual of creating tickets/issues/board-items (! not userstories) on the board, creating branches, pushing branches, creating merge requests, requesting review, doing review, incorporating review and (at some point) merging.

Links to the main 3 topical MRs/PRs:
- https://github.com/ww24e018/slm-tictactoe/pull/11
- https://github.com/ww24e018/slm-tictactoe/pull/19
- https://github.com/ww24e018/slm-tictactoe/pull/21

And links to the issues these close:
- https://github.com/ww24e018/slm-tictactoe/issues/10
- https://github.com/ww24e018/slm-tictactoe/issues/18
- https://github.com/ww24e018/slm-tictactoe/issues/20

Exemplary screenshot:
![[Pasted image 20260209103730.png|400]]

![[Pasted image 20260209105225.png|400]]

The suggestion made in the comment above lead to https://github.com/ww24e018/slm-tictactoe/issues/20 / https://github.com/ww24e018/slm-tictactoe/pull/21 .

### Technical description

The process resulted in 2 yaml files:
- `.github/workflows/maven.yml`
- `.github/workflows/maven-publish.yml`
These names are the default ones given by the github-actions wizard. Later the question turned up if those two (who have an identical build-command) could be unified.

It was assumed this would be possible but would/might require research into and testing of more advanced github-actions-syntax to distinguish between the different trigger-events.

For now - while possibly slightly inefficient - they satisfy requirements.



<div style="page-break-after: always;"></div>

## 010 - Working on User Stories

1. Once a user story is moved to `ready`, it is assigned to one or more contributors after checking in with each other in person. 
   ![[Pasted image 20260210110830.png|400]]
2. When contributor starts actively working on the story, they move it to `In progress`. 
   ![[Pasted image 20260210111200.png|200]]
3. A new branch is created (locally) and published to remote. 
   ![[signal-2026-02-10-111353_002.png|400]]
4. After the first commit ist ready, we push to remote and create a pull request which we mark as draft. This is to further visualize our work in progress to the rest of the team.
5. In our description we link the pull request to the issue.
   ![[signal-2026-02-10-114020.png|400]]
6. When the developer is done with the ticket and all checks have passed, they set the pull request to "ready for review", request a review and move the ticket to `In review`.  ![[Pasted image 20260210115442.png|400]]
   ![[Pasted image 20260210115457.png|400]]
	![[Pasted image 20260210115623.png|400]]
7. The reviewer writes a review. If there are no necessary changes, they can directly approve the request.![[Pasted image 20260210115958.png|400]]
8. After the pull request is approved, the developer merges to main and moves the ticket to `Done`.
   ![[Pasted image 20260210120150.png|400]]
9. Sometimes the reviewer has questions, remarks, recommendations or corrections. These are posted as comments. If necessary or useful, they are also discussed in person. The review is then submitted as requesting changes.
10. The author makes amends to the code and answers to the comments left by the reviewer. After changes have been made, they re-request a review.
11. The reviewer who requested the changes reviews the author's answers and changes to the code and ultimately resolves the conversation in the comments. 
    ![[Pasted image 20260210152947.png|400]]
12. Once they are satisfied with the result, they approve the pull request. Subsequently the feature branch is merged by the author (see steps 7-8).



## 011 - A final overview

A clean Kanban board - all issues have been moved to `done`:

Exemplary game run - everything works as it should:

Our big release:



