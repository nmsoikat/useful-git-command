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


Note (For Revert): 
- HEAD~1  => last 2 commit.
- HEAD~1..HEAD or HEAD~1.. => last 1 commit.

### git revert -n HEAD
A - B - C - D - E - F
1. `git revert HEAD HEAD~1 HEAD~2` or `git revert -n HEAD HEAD~1 HEAD~2`
    - Revert F, E, D
    - Create 3 new commit (use -n to create manual commit [1 commit] for all.)
    - Code state: Same as C

2. `git revert HEAD HEAD~3`
    - Revert F, C
    - Create 2 new commit
    - Code state: Same as B + D + E changes.

3. `git revert HEAD~3..HEAD` or `git revert HEAD~3..`
    - Revert D, E, F (NOT C)
    - Code state: Same as C changes

4. `git revert HEAD~3^..HEAD^0`
    - Reverts: C, D, E, F
    - Code state: Same as B
    
5. `git revert HEAD~3..HEAD^0`
    - Reverts: D, E, F
    - Code state: Same as C

**`-n`**
- Without -n (default) -> Revert and automatically commit.
- With -n -> Just revert you have to commit manually.