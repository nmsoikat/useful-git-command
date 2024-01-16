It would be better to revert the commits that you don't want, then push as normal.

`git revert commit-id`  revert the commit. then vim editor will open for save the commit message.

`git revert --no-commit commit-id` revert without commit. so that we can revert another commit id and 
commit "both revert in one commit". -n or --no-commit

`git commit -m "revert this and this commit"`

`git revert HEAD~3` Revert the changes specified by the "fourth last commit" in HEAD and create a new commit with the reverted changes.

`git revert -n master~5..master~2`
Revert the changes done by commits from the fifth last commit in master (included) to the third last commit in master (included), but do not create any commit with the reverted changes. The revert only modifies the working tree and the index.

`git revert -n HEAD~2..HEAD` last 2 commit
`git revert -n HEAD~2..` last 2 commit