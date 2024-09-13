# Multiple Git Account Maintain

### Step-1: Generate SSH Key For Each Account
- `ls .ssh` // Check is there any ssh added or not
- `ssh-keygen -t ed25519 -C "your_email@example.com"`
- type file name example: `id_personal_github_account` it will create two files with key. One for private and another for public
  1. id_personal_github_account //private key
  2. id_personal_github_account.pub // public key
- Press enter ... for default config
- Done
We can not use same key for multiple account. 

ssh-keygen: This is the command-line utility for generating SSH keys.

-t ed25519: This option specifies the type of key to create. In this case, it's specifying that the key should be generated using the Ed25519 algorithm. Ed25519 is a modern elliptic curve cryptography algorithm used for SSH key generation, known for its security and efficiency.

-C: This option is followed by a comment. The comment is typically used to identify the key, such as including an email address or any other relevant information. It's optional, but it can be helpful for managing multiple keys or for identifying the key's purpose.

```
Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux



### Step-2: Add This Key To SSH Agent
- `ssh-add -l` // show list that are added to ssh agent
- `ssh-add id_personal_github_account` // add private file
- `ssh-add -d file_name` // to delete from ssh agent

Err: Could not open a connection to your authentication agent.
Did You Start ssh-agent?
You might need to start ssh-agent before you run the ssh-add command:
```
eval `ssh-agent -s`
```
#### Important: Use the default terminal. Another terminal might not work (ex: fish terminal not work)
#### For multiple agents need configuration. If it does not work then, delete the agent and add a new one. because by default used the first one of `ssh-add -l`
```
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
```

Note: When we have multiple account added to ssh agent then first added key will be the default key. So, for managing the multiple account we have to use ssh config
follow Step 4.


### Step-3: Public Key Set Into Github Account
- `cat id_personal_github_account.pub` // it will show public key. copy the key
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
  IdentityFile ~/.ssh/id_rsa_personal_github

# Office Github Account
Host github-office
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_office_github

# Personal Gitlab Account
Host gitlab.com
  HostName gitlab.com
  User git
  IdentityFile ~/.ssh/id_rsa_personal_gitlab

```

Note:
- Host github.com -> `Host` can be anything it is an alias.
- HostName github.com -> `HostName` it is actual address for the alias.


### Step-5  Clone Multiple Repo
1. git@github.com:github_username/test-ssh.git
2. git@github-office:github_username/test.git

Breakdown:
`git@` -> git repo
`github-office:` -> alias
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



