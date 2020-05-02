# Random Learnings

**A repository to store random programming / tech things that I learn.**

Unless otherwise stated, square brackets in code snippets indicate a value to be used.

## Tools

### Design

[Adobe Color CC](https://color.adobe.com/create/color-wheel/)
[Material Design Color Tool](https://material.io/tools/color/#!/?view.left=0&view.right=0&primary.color=DCEDC8)

### AWS

[Simple AWS services](https://expeditedsecurity.com/aws-in-plain-english/)

### Command Line

#### Bash

Output to console and print to file, -a to append.

```bash
echo "any command" | tee myfile.txt
```

### Docker

Lint Dockerfile

```bash
# Install
sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.17.5/hadolint-Linux-x86_64
sudo chmod +x /bin/hadolint
# Lint
hadolint Dockerfile
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

### JS

Remove item from array at id

```js
let test =  [{firstName:'John', lastName:'Smith'},{firstName:'Jane', lastName:'Smith'},{firstName:'Billy', lastName:'Bob'}];
test.splice(1, 1);
```

Remove item(s) from array

```js
test.filter((value) => value.lastName!=='Bob');
```

### Windows Command Prompt

To change drive, do not use cd

```bash
C:

cd path/to/dir
```

## Source Control

### Git

Use cat instead of less for git branch / tag / etc.

```bash
git config --global core.pager cat
```

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

List story codes since latest tag (replace regex in grep)

```bash
# tags on current branch
git log HEAD...$(git describe --abbrev=0 --tags) --pretty=%s | grep -o 'BAU-\d*\|SUP-\d*' | sort -u

# tags on all branches
git log HEAD...$(git describe --tags `git rev-list --tags --max-count=1`) --pretty=%s | grep -o 'BAU-\d*\|SUP-\d*' | sort -u
```

Check if branch contains tag

```bash
git branch --contains $(git rev-parse your-tag) | grep '^master$'
```

### Github

Can use specified folder on master branch for gh-pages instead of specific branch.

## SQL

### Postgresql

Check if key exists in a json field for each record.

```sql
SELECT jsonField FROM tableName WHERE jsonField->>'jsonKey' IS NOT NULL
```
