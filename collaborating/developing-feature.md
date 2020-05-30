# Developping a feature

Here are the steps to follow to develop a feature (or bugfix, refactor, or any other kind of work).

- Create a branch, from the tip of the parent branch of this feature. Respect the branch naming conventions of the project.


## Development phase

- Implement your changes and commit them. [How to commit](/collaborating/how-to-commit.md)
- If, at any point during this phase, changes from parent branch are needed, [rebase on parent branch](/how-to/rebasing-further-on-parent-branch.md)


## Preparing for merge

- [Rebase on parent branch](/how-to/rebasing-further-on-parent-branch.md)
- [Clean branch history](/how-to/cleaning-branch-history.md)


## Review phase

- Ask the parent branch's owner for review
- Integrate review feedbacks **without altering history** (new commits only, no force push)
- Repeat this **Review phase** until there are no more feedbacks, and the feature has been validated


## Git review phase

- Ask the parent branch's owner for git review
- Integrate git review feedback WITHOUT CHANGES TO CODE (only alter commits; git diff with origin must be void)
- Repeat this **Git review phase** until there are no more feedbacks, and the commits structure has been validated


## Merge phase

- [Rebase on parent branch](/how-to/rebasing-further-on-parent-branch.md)
- From the parent branch, do a non-fast-forward merge of the feature branch (should be done by the parent branch's owner)
- Delete the remote branch (should be done by the parent branch's owner)
- Delete the local branch
