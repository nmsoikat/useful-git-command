# GIT STASH
The written code is not ready to commit. But we
want to switch the branch. For this use stash 😀

`git stash save “message 2”` To save the changes.
Stashing the current working directory's staged or
unstaged changes or untracked files.

`git stash list` To show the stash list.<br/>
Output (LIFO):<br/>
stash@{0}: On branch-name: message 2 <br/>
stash@{1}: On branch-name: message 1 <br/>

`git stash apply stash@{0}` To apply the stash. but not
removed from the stash list.

`git stash drop stash@{0}` To remove stash from the stash
list

`git stash pop` To apply and drop. It apply latest stash.
Note: stash@{0} is just a stash reference

`git stash save “message 2” -u` To save changes including
untracked file (new file).

`git stash show` To show changes before applying. It will count changes. <br/>
Output:<br/>
readme.md | 2 +-<br/>
1 file changed, 1 insertion(+), 1 deletion(-)

`git stash show -p` To show details changes before applying.
It will show with a patch view.
Note: For untracked files use -u flag. We can use both
together -p -u

`git stash show stash@{0}` To show Individual stash by using
stash reference stash@{0}

`git stash clear` To drop all stash from the stash list

`git stash branch demo` To create a branch from the latest
stash

`git stash branch demo stash@{0}` To create a branch from a
specific stash.

`git stash save “message 2”`
=> The message is optional, we can use `git stash save` or
`git stash` to save the changes without any message.

#### Stash Format Breakdown:
Example: stash@{0}: WIP on auth: 0857051 “message 2”<br/>
stash@{0} => Stash reference<br/>
WIP => Work In progress<br/>
auth => auth is the branch name, the stash was created on
the branch<br/>
0857051 => commit hash<br/>
Thank you!
