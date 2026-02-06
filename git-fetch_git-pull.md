`git fetch` => fetch
`git pull` => fetch + merge
`git fetch --prune` => command is a way to delete all the objects that are not reachable from the remote repository.
The primary use of git prune is to clean up your working directory after you have finished working on a project.

`git config --global fetch.prune true` => prune flag auto apply 
whenever use `get fetch`

**git pull warning:**
hint: You have divergent branches and need to specify how to reconcile them.
- `git pull --ff-only` first forward only
- `git pull --no-rebase` merge
- `git pull --rebase` rebase