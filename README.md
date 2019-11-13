# Random Learnings

**A repository to store random programming / tech things that I learn.**

Unless otherwise stated, square brackets in code snippets indicate a value to be used.

## Tools

### Design

[Adobe Color CC](https://color.adobe.com/create/color-wheel/)
[Material Design Color Tool](https://material.io/tools/color/#!/?view.left=0&view.right=0&primary.color=DCEDC8)

## Command Line

### Bash

Output to console and print to file, -a to append.

```bash
echo "any command" | tee myfile.txt
```

### HTML

[HTML HEAD explained](https://htmlhead.dev/)

### Markdown

Add a comment to the markdown file (won't be included in conversion of the file):

```markdown
[empty line]
[//]: # (Your comment here!)
```

[//]: # (Your comment here!)

### Node.js

[Setting up a nodejs cache (useful for build boxes)](https://www.nullivex.com/blog/setting-up-a-nodejs-dist-mirror)

### Windows Command Prompt

To change drive, do not use cd

```bash
C:

cd path/to/dir
```

## Source Control

### Git

Create an empty branch, e.g. for gh-pages

```bash
git checkout --orphan <branch name>

rm -rf ./*

git rm --cached -r .
```

Revert commit a commit

```bash
git revert <commit id>
```

Revert a merged commit

```bash
git revert -m 1 <merge id>
```

Delete a remote branch

```bash
git push --delete <remote_name> <branch_name>
```

### Github

Can use specified folder on master branch for gh-pages instead of specific branch.
