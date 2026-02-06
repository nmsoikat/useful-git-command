## On main
- `git checkout -b feature6`
- `git merge bug_fix`
- `git merge hot_fix`


### Result
- You have TWO merge commits, not one merge with two parents
```
main ─── A
         |
         └─ feature6 ─── M1 (merge bug_fix) ─── M2 (merge hot_fix)
                        /                      /
             bug_fix ──┘            hot_fix ──┘
```
* M1 has 2 parents: feature6 + bug_fix
* M2 has 2 parents: M1 + hot_fix


**To Get ONE Merge with 2 Parents Use `octopus merge` (merge both at once)**
- `git checkout -b feature6`
- `git merge bug_fix hot_fix`

### Result
```
main ─── A
         |
         └─ feature6 ─── M (octopus merge)
                        / \
             bug_fix ──┘   └── hot_fix
```
* M has 3 parents: feature6 + bug_fix + hot_fix


**Remember: Each merge creates a new commit**
So HEAD^1, HEAD^2, HEAD^3 all work!