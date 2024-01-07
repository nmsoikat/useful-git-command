Git Restore: Discard changes or Unstage staged files. Restore not work for untracked file.
(undo the `git add .`)

`git restore .` => Discard all changed
`git restore test.js` => Discard all changed for specific file.

`git restore --staged .` => Unstage all staged files. 
`git restore --staged test.js` => Unstage specific staged files.