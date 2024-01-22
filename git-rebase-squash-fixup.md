Rebase: Clean your un-cline commit history 
`git rebase main` => Lets say our current branch is feature.
- Find "last match commit" for both.
- For Feature Branch: Store to one hand, latest commits "that are not match" with main
- Take all latest commits into Feature Branch from main branch "that are not match".
- Now apply serially all commits of Feature branch "that was store one side"

Conflict:
- fix the conflict then apply `git rebase --continue` commit message and done.
or use `git rebase --abort` => To cancel the rebase process and back to normal.

Rebase using Interactive Shell:
`git rebase -i HEAD~5` => -i (Interactive shell)
- editor will open and press i for insert
- remove pick and type s (squash) on start of each commit
- Ex:
pick 121211 first commit
squash 121212 second commit
squash 121213 third commit
- output: second and third commit squash into first commit. same for fixup

Squash: Combine 5 commit to one commit. 
now `git log --oneline` will show the one commit for five commit.
but for `git log` will show combined all five commit

Fixup: If we choose f (fixup) instead of s (squash) 
then, `git log --oneline` and `git log` both will show one commit for five commit.

Reword: If we choose r (reword) Edit your commit message. (amend work on reset commit)

Drop: If we choose d (drop) Delete the commit using interactive rebase.

Reorder: Just reorder the line in interactive rebase shell. done.

Split commit: We have made a commit. latter we realizes and we want to create more commit from the single commit.

- choose e (edit) (:WQ) then git will take you in special branch 
  [branch-name|rebase -i]
- git status => interactive rebase in progress message will show
- unstage the commit that you want to split
- `git reset commit-id` => Go to that commit. and all changes will remain as unstage.
- Now create you commit one by one as your wish.
- `git rebase --continue` => Git will continue the rebase process and finish it. then take you back to normal branch