Rebase: Clean your un-cline commit history 
`git rebase main` => Lets say our current branch is feature.
- Find "last match commit" for both.
- For Feature Branch: Store to one hand, latest commits "that are not match" with main
- Take all latest commits into Feature Branch from main branch "that are not match".
- Now apply serially all commits of Feature branch "that was store one side"

Conflict:
- fix the conflict then apply `git rebase --continue` commit message and done.
or use `git rebase --abort` => To cancel the rebase process and back to normal.

`git rebase -i HEAD~5` => -i (Interactive shell)
- editor will open and press i for insert
- remove pick and type s (squash) on start of each commit

Squash: Combine 5 commit to one commit. 
now `git log --oneline` will show the one commit for five commit.
but for `git log` will show combined all five commit

Fixup: If we choose f (fixup) instead of s (squash) 
then, `git log --oneline` and `git log` both will show one commit for five commit.