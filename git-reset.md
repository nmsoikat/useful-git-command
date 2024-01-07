Git Reset: used to undo the changes in your working directory and get back to a specific commit.

`git reset commit-id` => Go to that commit. and all changes will remain as unstage.
`git reset --hard commit-id` => Go to that commit. Removed changes until that commit.

`git reset HEAD~1` => Go back 1 commit. and all changes will remain as unstage.
`git reset --hard HEAD~1` => Go back 1 commit. Removed changes until that commit.