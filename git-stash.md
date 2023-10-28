# GIT STASH
The written code is not ready to commit. But we want to switch the branch. For this use stash 😀

### Save Stash
- `git stash` Or `git stash save`
- `git stash save “message 2”`
- `git stash save “message 2” -u`

`git stash save “message 2”` To save the changes.  
Stashing the current working directory's staged or unstaged changes or untracked files.  
The message is optional, we can use `git stash save` or `git stash` to save the changes without any message.

`git stash save “message 2” -u` To save changes including untracked file (new file).

### View Stash
- `git stash list`
- `git stash show`
- `git stash show -p`
- `git stash show stash@{0}`
- `git stash show stash@{0} -p`
- `git stash show stash@{0} -p -u`

`git stash list` To show the stash list.  
Output (LIFO):  
stash@{0}: On branch-name: message 2  
stash@{1}: On branch-name: message 1  

`git stash show` To show changes before applying. It will count changes.  
Output:  
readme.md | 2 +-  
1 file changed, 1 insertion(+), 1 deletion(-)

`git stash show -p` To show details changes before applying. It will show with a patch view.  
Note: For untracked files use -u flag. We can use both
together -p -u

`git stash show stash@{0}` To show Individual stash by using stash reference stash@{0}


### Apply and Drop
- `git stash apply stash@{0}`
- `git stash drop stash@{0}`
- `git stash pop`
- `git stash clear`

`git stash apply stash@{0}` To apply the stash. but not removed from the stash list.

`git stash drop stash@{0}` To remove stash from the stash list

`git stash pop` To apply and drop. It apply latest stash. 

`git stash clear` To drop all stash from the stash list


### Create Branch From Stash
- `git stash branch demo`
- `git stash branch demo stash@{0}`

`git stash branch demo` To create a branch from the latest
stash

`git stash branch demo stash@{0}` To create a branch from a specific stash.


### Stash Format Breakdown:
Example: stash@{0}: WIP on auth: 0857051 “message 2”  
stash@{0} => Stash reference  
WIP => Work In progress  
auth => auth is the branch name, the stash was created on
the branch  
0857051 => commit hash  
Thank you!
