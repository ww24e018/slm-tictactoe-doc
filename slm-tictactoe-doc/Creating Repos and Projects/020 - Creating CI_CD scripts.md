
# The process of research and development

To simplify research and development, and to keep the submission repo free of 10^2 commits doing trial and error on syntax and meaning, a decision was made to use a custom test-repository on github to experiment more freely.

This repository is also public and is available [here](https://github.com/ww24e018/slm-tictactoe-test) if a deeper view into that process is required. It does not have the full spectrum of main-branch protections:

![[Pasted image 20260209103218.png]]

# The process of implementing results

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
![[Pasted image 20260209103730.png]]

![[Pasted image 20260209105225.png]]

The suggestion made in the comment above was realised in https://github.com/ww24e018/slm-tictactoe/issues/20 / https://github.com/ww24e018/slm-tictactoe/pull/21 .

# Technical description

The process resulted in 2 yaml files:
- `.github/workflows/maven.yml`
- `.github/workflows/maven-publish.yml`
These names are the default ones given by the github-actions wizard. Later the question turned up if those two (who have an identical build-command) could be unified.

It was assumed this would be possible but would/might require research into and testing of more advanced github-actions-syntax to distinguish between the different trigger-events.

For now - while possibly slightly inefficient - they satisfy requirements.








