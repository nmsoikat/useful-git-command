`git commit` => It will open interactive shell to type commit message.

`git commit -am "Add all and commit"` => not work for untracked(new file) file.
`git commit -m "Not a correct commit message"`
`git commit --amend -m "Correct the commit message"`

`git commit --amend` => Add another changes with recent commit. So we do not need to create extra commit.
`git commit --amend --no-edit`

`git rm --cached private.js` => file will not added to staging. like as .gitignore

`git rm -r --cached privateFolder/` => -r (recursive) flag for folder.