# Resolving rebase conflicts

When rebasing commits onto a new parent, you might encounter conflicts if this new parent modified the same files as some of the commits you're rebasing.

In the case of a rebase, conflicts are commit-specific. If you're rebasing 5 commits, you'll go over each of these 5 commits one by one, and each of them may, or may not, have conflicts.
This makes it very convenient to resolve conflicts, because it can be done step by step, especially if your commits are well made and split correctly.

If a commit has conflicts, you'll have to resolve them as usual, then add the modified files, then run `git rebase --continue`.
This will apply your changes (conflicts resolutions) to the concerned commit, then proceed to the next commit, which may (or may not) have its own conflicts to resolve.

The main difference between rebase and merge conflicts resolution, is that all the merge conflict resolutions are stored in a single merge commit, whereas, as mentionned earlier, every conflict resolved during a rebase will be applied to the concerned commit. There will be no merge commit.
