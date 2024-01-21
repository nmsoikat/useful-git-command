`git merge branch-name` => merge local branch
`git merge origin/branch-name` => merge from remote branch
`git merge branch-name --squash` => Squash merge. Take single commit instead all commit of "branch-name"
- Merge and take all changes in staging area
- Now, commit for these change. commit for this squash merge.


Three Way Merge: 
1. Last time created new-branch from master branch.
2. Do some work.
3. Now you want to merge new-branch into master branch.
4. But, in the mean time master branch has more commit than you created new-branch
5. Now three way merge will happen

Fast-Forward Merge (Two way merge):
1. (1-3) point are same
2. If master branch is same as before when you created new-branch from master.
3. Fast-Forward merge will happen

`git merge branch-name --no-ff` => when you do not want to fast-forward merge.

Conflict:
- `git status` => show which file has conflict
- `git log --merge --oneline` => which commits are created conflict
- Fix the conflict then add and commit
- Otherwise: `git merge --abort` => Merge conflict then we can use --abort to cancel the merge process and back to normal.