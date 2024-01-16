Git Reset: used to undo the changes in your working directory and get back to a specific commit.

`git reset commit-id` => Go to that commit. and all changes will remain as unstage.
`git reset --hard commit-id` => Go to that commit. Removed changes until that commit.

`git reset HEAD~1` => Go back 1 commit. and all changes will remain as unstage.
`git reset --hard HEAD~1` => Go back 1 commit. Removed changes until that commit.

`git reset --hard HEAD^` => Go back one commit.

Remote branch:
`git reset --hard commit-id`
`git push -f origin feature`



Note: https://stackoverflow.com/questions/5816688/resetting-remote-to-a-certain-commit