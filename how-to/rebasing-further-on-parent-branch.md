# Rebasing a branch further on its parent branch

When you fork (create) a branch A from a branch B, it is often useful to rebase your branch A on top of the parent branch B.
That's what you'll want to do when you want your branch A to catch up with the latest updates of the parent branch B.

Doing so is extremely simple: checkout on your branch A, then simply run: `git rebase B`.
This will rebase your branch A on top of B.

If some parts of the code were modified on both A and B, you might need to resolve some conflicts. See [Resolving rebase conflicts](resolving-rebase-conflicts.md).
