# Branch protection level

A project has multiple branches, all of them being forked from another branch.
Depending on their type, and how many collaborators are active on these branches, each of them has a different **protection level**.

The **protection level** of a branch represents who is allowed to push commits to this branch, and who is allowed to edit its history (by force pushing).


## Prevent people from pushing to some branch

The reason why we want to prevent some people from pushing commits to a branch, is to have someone else review these commits before they end up on the branch.
In this case, our main branch would have one or more reviewers, allowed to push to it, and other people should first push their commits to another branch, so the reviewers can review their commits before merging them to our main branch.


## Prevent people from editing history (force pushing)

The reason why we want to prevent some people to edit a branch's history, is because it is extremely difficult for multiple people to work on the same branch while editing history, and it can lead to catastrophic situations (excessive conflicts, loss of code, ...).
General rule is to never edit the history of a branch where other people work.
Only editing the history of branches you own is ok.
If you own a branch where other people are working, you should be very careful and responsible about rewriting history, and always be sure of what you're doing.
