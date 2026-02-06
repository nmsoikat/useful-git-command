### git rebase
Clean your un-cline commit history 

Workflow:
`git rebase main` => Lets say our current branch is `feature`.
- Find "last match commit" for both.
- For Feature Branch: Store to one hand "that are not match with main"
- Take all latest commits into feature branch from main branch.
- Now apply serially all commits of Feature branch "that was store one side"

**Details actin: develop branch rebase into feature branch**
- checkout to develop branch and take pull
- checkout to feature branch 
- rebase develop

**Simple action**
you are in feature branch.
*`git pull origin develop`**
1. git fetch origin
2. git merge origin/develop

**`git pull --rebase origin develop`**
1. git fetch origin develop
2. git rebase origin/develop

**`git rebase origin/develop`**
1. git fetch origin
2. git rebase origin/develop

Conflict: better use `git rebase --abort` and do normal merge.
- fix conflict and `git add .` and `commit` then `git rebase --continue`
- fix again if any and `add` `commit` and then `--continue`. until finish.

You have divergent branches and need to specify how to reconcile them.:
- `git pull --ff-only origin develop` not possible
- `git pull --no-rebase origin develop` merge
- `git pull --rebase origin develop` rebase