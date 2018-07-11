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

Can use /docs folder on master branch for gh-pages instead of specific branch.
