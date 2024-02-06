### Reflog Reference Log
It is save all activity of local repository. work only for local this log dose not push to remote repository. and this log has expire date.

`git reflog show` To shows the reflog of (HEAD, by default). 
`git reflog show feature` To show target branch reflog.

Aside: understanding the reflog means you can't really lose data from your repo once it's been committed. If you accidentally reset to an older commit, or rebase wrongly, or any other operation that visually "removes" commits, you can use the reflog to see where you were before and `git reset --hard` "back to that ref to restore your previous state". Remember, refs imply not just the commit but the entire history behind it.

By default, the reflog expiration date is set to 90 days.

`git reset --hard commit-id` To go forward/backward
it is possible for reflog.

Note: 
https://stackoverflow.com/questions/17857723/whats-the-difference-between-git-reflog-and-log