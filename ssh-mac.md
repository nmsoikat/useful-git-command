#### in -> users/username/.ssh/

- ssh-keygen -t ed25519 -C "nursaykat@gmail.com"
- eval "$(ssh-agent -s)"
- touch config

```
# Github Account (Default)
Host github.com
  HostName github.com
  AddKeysToAgent yes
  User git
  IdentityFile ~/.ssh/ssh_gh_mac
```

- ssh-add --apple-use-keychain ~/.ssh/ssh_gh_mac
