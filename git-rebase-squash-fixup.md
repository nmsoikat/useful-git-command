`git rebase -i HEAD~5` => -i (Interactive shell)
- editor will open and press i for insert
- remove pick and type s (squash) on start of each commit

Squash: Combine 5 commit to one commit. 
now `git log --oneline` will show the one commit for five commit.
but for `git log` will show combined all five commit

Fixup: If we choose f (fixup) instead of s (squash) 
then, `git log --oneline` and `git log` both will show one commit for five commit.