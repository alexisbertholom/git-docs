# Pull-rebase


## Explaination

Git has 2 ways of pulling commits from the remote:
- pull-merge, which is the default
- pull-rebase, which require a bit more knowledge, but is better most cases

When using `git pull`, two things happen:
- first, a `git fetch`, which fetches changes from the remote to update your remote-tracking branches, for example `origin/my-branch`
- then, either a `git merge origin/my-branch` in pull-merge mode, or a `git rebase origin/my-branch` in pull-rebase mode

In pull-merge mode, you'll end up with a merge commit between your local commits and the remote commits. This is bad most of the time, as this merge commit is completely irrelevant, and its sole purpose is to avoid altering your local history.

But the only history that we should avoid altering is the remote one, because that would affect other developers.
Altering your local history isn't bad, and in this specific case, its the best thing to do.
With pull-rebase, your local commits will be rebased on top of the remote version of the branch (on top of `origin/my-branch`).

This completely removes the need for a merge commit, and allows us to keep our history clean.

Like any pull, you might have conflicts to resolve. In this case, see [Resolving rebase conflicts](/how-to/resolving-rebase-conflicts.md)


## Configuring git

The most convenient thing to do is to configure git to always pull in rebase mode by default.

To do so, make sure your git version is >= 1.7.9, then run: `git config --global pull.rebase true`.

This will make sure everytime you `git pull`, it behaves as `git pull --rebase`.
