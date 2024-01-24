### What are git TAGs
Tagging in git or any other VCS (Version Control System) refers to creating specific points in history for your repository/data.
This is usually done to mark release points. (ex: v1.0.1)
Tag is like a branch but we can not create farther commit from tag

                                                       tag1
MasterBranch -> commitId1 -> commitId2 -> commitId3 -> commitId4
commitId4 and tag1 both are pointing the same reference

### Why should I create TAGs
1. To mark release point for you code/data
2. To create historic restore point.

### When to create TAGs
1. When you want to create a release point for stable version of you code.
2. When you want to create a historic point for your code/data that you can refer at
any future time (To restore your code/data).

### How to create TAGs
1. Checkout the branch where you want to create the tag.
`git checkout master`
2. Create tag with some name
`git tag tag-name` in our case v1.0
`git tag` to show tag list
`git show v1.0` show tag details 
(latest commit will show if tag is not annotated tag/lightweight tag). 
Tag details will show if tag is annotated.

Create Annotated Tag (recommended): Annotated tags are stored as full objects in the Git database. To reiterate, They store extra meta data such as: the tagger name, email, and date. Similar to commits and commit messages Annotated tags have a tagging message.
`git tag -a v1.1 -m "as like commit message"`

3. Showing tag
`git tag`
`git show v1.1`
`git show -l "v1.*"` using -l flag we care use * (Wildcard) to find matches.

4. Push tag to remote
`git push origin tag-name` in our case v1.0
`git push origin --tags` push all tags at once
`git push --tags` push all tags at once

5. Delete tag
`git tag -d v1.0`

Remote:
`git push origin -d v1.0` Delete tag from remote

6. So far we create tag for last commit or current commit.
when we want to create tag for specific commit.
`git tag tag-name commit-id`

7. Note:
Git tags are just pointers to the commit. So you use them the same way as you do "HEAD, branch names or commit sha hashes". You can use tags with any git command that accepts commit/revision arguments. You can try it with `git rev-parse tagname` to display the commit it points to.

`git rev-parse v1.1` => To display the commit it points to.


### Git TAGs VS Release.
- Tag is pointer of a commit. tag refer to a commit.
- We can create release from tag. We can upload build folder or Executable file with release. and share the release link So that user can download specific version.
