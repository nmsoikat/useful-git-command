# Multiple Git Account Maintain (Windows)

### Step-1: Generate SSH Key For Each Account
- create `.ssh` folder into `C:\User\username\` 
- `ssh-keygen`
- type file name example: `personal_id_rsa` it will create two files with key. One for private and another for public
  1. personal_id_rsa //private key
  2. personal_id_rsa.pub // public key
- Press enter ... for default config
- Done
We can not use same key for multiple account. 

### Step-2: Add This Key To SSH Agent
1. Start ssh agent (extra step then linux)
    - Open gitbash
    - eval `ssh-agent -s`
2. `ssh-add personal_id_rsa` // add private file

Note: When we have multiple account added to ssh agent then first added key will be the default key. So, for managing the multiple account we have to use ssh config
follow Step 4.


### Step-3: Public Key Set Into Github Account
- `cat personal_id_rsa.pub` // it will show public key. copy the key
- Goto github account -> Setting -> SSH Key and GPG Keys -> New SSH Key
- Paste public key that are coped from terminal.
- Add SSH Key // Done


### Step-4: SSH Configuration
- `ls .ssh` if there is no `config` file the create one.
- `touch .ssh/config` to create a `config file` into `.ssh` folder
- Write these configuration into config file.
```
# Personal Github Account (Default)
Host github.com
  HostName github.com
  User git
  IdentityFile C:\Users\nmsoikat\.ssh\personal_id_rsa

# Office Github Account
Host office
  HostName github.com
  User git
  IdentityFile C:\Users\nmsoikat\.ssh\office_id_rsa

# Personal Gitlab Account
# Host gitlab.com
#   HostName gitlab.com
#   User git
#   IdentityFile ~/.ssh/id_rsa_personal_gitlab

```

Note:
- Host github.com -> `Host` can be anything it is an alias.
- HostName github.com -> `HostName` it is actual address for the alias.


### Step-5  Clone Multiple Repo
1. git@github.com:github_username/test-ssh.git
2. git@office:github_username/test.git

Breakdown:
`git@` -> git repo
`office:` -> alias
`github_username/test.git` -> github username and repo name


Ref:
- https://gist.github.com/jexchan/2351996


# Change User
All repository will use these username and email by default
- `git config --global user.name "github_username"`
- `git config --global user.email "github_email"`

Particular repos username and email. Just remove --global flag
- `git config user.name "github_username"`
- `git config user.email "github_email"`




