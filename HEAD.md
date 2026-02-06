#### What is HEAD?
- Pointer to your current commit (where you are right now)
- `HEAD` must be capital.

**HEAD Notation`~`**
HEAD or HEAD~0 = F (0 current commit)
HEAD~1 = E (1 commit back)
HEAD~2 = D (2 commits back)
HEAD~3 = C (3 commits back)
HEAD~4 = B
HEAD~5 = A

**Alternative Notation`^`**
- Any commit (Parent of)
HEAD    = HEAD (current)
HEAD^   = HEAD~1 (parent)
HEAD^^  = HEAD~2 (grandparent)
HEAD~2^ = HEAD~3 (parent of HEAD~2)

- Merge only
HEAD^0 = HEAD (current)
HEAD^1 = HEAD~1

**Range Notation**
A - B - C - D - E - F (HEAD)
            ↑       ↑
         HEAD~2    HEAD
* HEAD~2..HEAD = E (NOT D, NOT F) Excludes both ends.
* HEAD HEAD~2 = F, E, D Include both ends.
HEAD HEAD~2
  ↑    ↑
 (F)  (D)
* `..` always exclude both end commit. but we can force include last end commit by using `^0` 
* Use `~` for going back in history, for merge parent `^`


**`^`Has TWO different meanings depending on position**
1. `^` AFTER a commit = `parent of`. This works on ANY commit, not just merges.
HEAD^    # Parent of HEAD (same as HEAD~1)
HEAD~3^  # Parent of HEAD~3

2. `^` BEFORE a number = "which parent" (merge only)
HEAD^0  # Current HEAD
HEAD^1  # First parent (merge or regular)
HEAD^2  # Second parent (MERGE ONLY)
HEAD^3  # Third parent (rare case, but if use octopus merge)

[Merge parent example](git-merge-parent-example.md)
