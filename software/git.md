# Git

Use cat instead of less for git branch / tag / etc.

```bash
git config --global core.pager cat
```

**WARNING: Ruins git log!!**

Could also pipe command into cat

```bash
git branch | cat
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

Add existing folder to repo:

```bash
git init
git add .;git commit -m'my first commit'
git remote add origin https|ssh:path/to/the/repository.git
git pull origin master --allow-unrelated-histories
git push -u origin master
```
