### What are git TAGs
Tagging in git or any other VCS (Version Control System) refers to creating specific points in history for your repository/data.
This is usually done to mark release points. (ex: v1.0.1)

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
`git show v1.0` show tag details (latest commit will show if tag is not annotated tag). Tag details will show if tag is annotated.

Create Annotated Tag: Annotated tags are stored as full objects in the Git database. To reiterate, They store extra meta data such as: the tagger name, email, and date. Similar to commits and commit messages Annotated tags have a tagging message.
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