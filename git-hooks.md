pre-commit file for execute before commit.
post-commit file for execute after commit.

Workflow:
- Goto git hooks folder `cd .git/hooks/`
- Create a hooks file `touch pre-commit` without any extension.
- Write some script that will execute before commit. Example:
```
#! /bin/bash
echo "Pre commit executed!"
```
- Make executable `chmod +x pre-commit`
