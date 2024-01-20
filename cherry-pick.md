Cherry Pick: As like 'git merge' and 'git rebase', but Instead of getting all commit. We can pick just one commit (we can merge one or more commit by select) using Cherry Pick.

Note: Lets say I am in Main branch and I have provided feature branch commit id
`git cherry-pick commit-id` => single
`git cherry-pick commit-id commit-id` => multiple

Conflict:
`git cherry-pick --abort` => Close cherry pick process. and everything going back to normal.
Otherwise, fix the Conflict then.
`git add `
`git cherry-pick --continue` => commit message and done.