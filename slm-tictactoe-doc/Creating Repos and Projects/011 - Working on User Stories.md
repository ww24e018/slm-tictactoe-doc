
1. Once a user story is moved to `ready`, it is assigned to one or more contributors after checking in with each other in person. ![[Pasted image 20260210110830.png]]
2. When contributor starts actively working on the story, they move it to `In progress`. ![[Pasted image 20260210111200.png]]
3. A new branch is created (locally) and published to remote. ![[signal-2026-02-10-111353_002.png]]
4. After the first commit ist ready, we push to remote and create a pull request which we mark as draft. This is to further visualize our work in progress to the rest of the team.
5. In our description we link the pull request to the issue.
   ![[signal-2026-02-10-114020.png]]
6. When the developer is done with the ticket and all checks have passed, they set the pull request to "ready for review", request a review and move the ticket to `In review`.  ![[Pasted image 20260210115442.png]]
   ![[Pasted image 20260210115457.png]]
	![[Pasted image 20260210115623.png]]
7. The reviewer writes a review. If there are no necessary changes, they can directly approve the request.![[Pasted image 20260210115958.png]]
8. After the pull request is approved, the developer merges to main and moves the ticket to `Done`.
   ![[Pasted image 20260210120150.png]]
9. Sometimes the reviewer has questions, remarks, recommendations or corrections. These are posted as comments. If necessary or useful, they are also discussed in person. The review is then submitted as requesting changes.
10. The author makes amends to the code and answers to the comments left by the reviewer. After changes have been made, they re-request a review.
11. The reviewer who requested the changes reviews the author's answers and changes to the code and ultimately resolves the conversation in the comments. 
    ![[Pasted image 20260210152947.png]]
12. Once they are satisfied with the result, they approve the pull request. Subsequently the feature branch is merged by the author (see steps 7-8).