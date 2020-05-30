# How to commit / naming commits

A good commit is a commit that will be easily readable and understandable.


## Commit contents

- A commit should only contain one logical change to the project.
- Do not commit changes unrelated to your commit (for example, don't implent a feature and do unrelated code formatting in the same commit)
- Good balance must be found between many small commits and one big commit. Commits should be split logically, not because of their size.
- Changes related to a feature don't need to be all in the same commit. If it makes sense to split the feature into several commits, you should do it.
- The order of commits is important: if a commit A depends on a commit B, B should be a parent of A (first commit B, then A).


## Commit message

### Goal

A commit's message has different role compared to a commit's contents.
The message's role is to describe **what does the commit do**.
The content's role is to describe **how does the commit do that**.
A message shouldn't describe **how is that done**; if someone needs that information, he will look at the commit's content.

A commit's message is the first thing that a collaborator will see.
As such, if it is good enough, the collaborator will only need the message to understand the commit, and won't even have to look at the commit's contents.

This should be your goal: making commits where reading only the message is enough to know exactly what it does.

### Specification

All commit messages should follow this specification: http://karma-runner.github.io/3.0/dev/git-commit-msg.html

We slightly modified this specification to add some more `<type>` values, that will be described next.


## Commit types

Depending on what kind of changes it contains, a commit will have a type.
Here are the possible commit types, that should be specified in the commit name, as seen in previous section:

- **fix**: fix a bug or issue introduced by a previous commit. These changes affect the end user.
- **feat**: add, remove, or change the behaviour of a feature. These changes affect the end user.
- **refactor**: rework code without changing any behaviour. These changes are code-only, and don't affect the end user.
- **style**: change code style and formatting.  These changes are code-only, and don't affect the end user.

- **docs**: changes to the documentation, either in dedicated doc files, or using code comments.
- **test**: changes to tests.
- **chore**: commits concerning automated tasks.

- **deps**: install/remove/update project dependencies. On a NodeJS project, these commits contain package.json and yarn.lock files.
- **perf**: improve performances without changing behaviour. These changes affect the end user.

A commit can only have one type.
If it contains multiple kind of changes, it should be split into multiple commits, each with the appropriate type.
