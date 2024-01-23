### What are git TAGs
Tagging in git or any other VCS (Version Control System) refers to creating specific points in history for your repository/data.
This is usually done to mark release points. (ex: v1.0.1)

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
`git tag tag-name` in our case v1.0.0
`git tag` to show tag list
`git show v1.4` show tag details (nothing will show if tag is not annotated tag)

Create Annotated Tag: Annotated tags are stored as full objects in the Git database. To reiterate, They store extra meta data such as: the tagger name, email, and date. Similar to commits and commit messages Annotated tags have a tagging message.
