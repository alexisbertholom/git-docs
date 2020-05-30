# Cleaning a branch's history


## Definition

Cleaning a branch's history means rewritting its commits so that we only keep useful information.
Useful information is commits that serve a purpose in being kept.
Once the feature is over, what matters is **the final result**, not **how we reached it through multiple iterations**.
So, we want to discard commits/modifications that cancel each other, as they are not part of the **final result**.
The remaining commits after we finished cleaning the branch should only contain modifications that are part of the **final result**.

Only clean branches should be merged with their parent branches, so the final branches have an history as clean as possible.


## Explanation

When working on a feature, there's usually several iterations before we get it right: maybe the right idea for this feature came later during development, so refactoring was needed; or maybe the specifications of the feature changed midway; or perhaps some early part of the feature was poorly designed, and had to be changed later...
By committing frequently, we might end up with a lot of commits on our branch, representing how the feature progressed chronologically.
In the end, the **final result** will be good, but we'll still have this heavy history of what happened over time during the development phase.

This history might not be necessary once we want to merge the branch with its parent.
The useful information we want to keep is the diff between the **parent branch** and the fully implemented feature, the **final result**.

So, ideally, we want to discard chronological information, and only keep a concise list of commits, representing **what changed compared to the parent branch**, without all the iterations needed for these changes to happen.


## Goal

The first step in this process of cleaning history is to define our goal.
We need to look at the differences between our **finished feature** and the **parent branch**, and organize these modifications into a short, logical list of commits.
The order of these commits should not be chronological; it should be dependency-based: the most generic commits (A) come first, the most specific commits (B) come last (considering B depends on A).


## How to achieve it

Achieving this goal might require to rewrite a lot of commits (through rebase, or other means).

There isn't only one good way to realize it.
But there is one that is usually easier than the others, so you can consider using it if you're not familiar with git.

First step is to discard all your commits, while keeping their contents as unstaged changes: `git reset fork-point-with-parent-branch` (fork-point-with-parent-branch is the last common ancestor between your branch and its parent).
Next step is to create only clean commits from these unstaged changes, using `git add -p` for partial add if needed.
And that's it. With these few steps, you've completely rewritten your history, discarding all the unwanted information.

This method has 2 main drawbacks though, that's why you shouldn't rely only on it, but should rather be familiar with git:
- you have to rewrite ALL of your commits, even the ones you could have kept
- on major feature branches, resetting all your work might give you a lot of unstaged changes, that will be hard to process and divide into commits.


## When to (or not to) clean branches

Cleaning a branch is rewritting history.
As you should know, you should be **extremely** careful with rewritting remote history (history of pushed branches).
Check [Branch protection level](/contributing/branch-protection-level.md).
Only clean the history of branches you own, and communicate efficiently with other people concerned with this branch so they know what you're doing.
