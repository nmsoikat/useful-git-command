### git rebase -i
Rebase using Interactive Shell:
1. `git rebase -i HEAD~5` -> open interactive shell with last 5 commit.
- press `i` for insert
- press `esc` stop editing.
- type `:wq` write and quit.
- type `:q!` quite without write.

2. Rename commit
- remove `pick` and write `reword`
- save

3. Second editor open with `reword` commit
- rename the commit
- save
- if you have select multiple `reword` then this process will apply for each.
- save

4. Rebase done. Now push
- `git push --force-with-lease origin feature`
- done.

* `--force` or `-f` Doesn't care if someone else pushed in the meantime
* `--force-with-lease` Fails if someone pushed since your last fetch or pushed in the meantime.

**Squash:**
- Combine 5 commit to one commit. 
- now `git log --oneline` will show the one commit for five commit.
- but for `git log` will show combined all five commit

**Fixup:** 
- If we choose f (fixup) instead of s (squash) 
- then, `git log --oneline` and `git log` both will show one commit for five commit.

**Drop:** If we choose d (drop) Delete the commit using interactive rebase.

Reorder: Just reorder the line in interactive rebase shell. done.



**Other**
Split commit: We have made a commit. latter we realizes and we want to create more commit from the single commit.

- choose e (edit) (:WQ) then git will take you in special branch 
  [branch-name|rebase -i]
- git status => interactive rebase in progress message will show
- unstage the commit that you want to split
- `git reset commit-id` => Go to that commit. and all changes will remain as unstage.
- Now create you commit one by one as your wish.
- `git rebase --continue` => Git will continue the rebase process and finish it. then take you back to normal branch

git rebase -i HEAD~3  # Rebase last 3 commits
git rebase -i <commit-hash>  # Rebase from specific commit
git rebase -i main  # Rebase all commits since branching from main