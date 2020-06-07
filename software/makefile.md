# Makefile

**_USE TABS!!_**

## Example Makefile

```makefile
.PHONY: help major minor patch prepareDevelop pullRequest

REPOSITORY_NAME := $(shell basename -s .git $(shell git config --get remote.origin.url))

help:           ## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'

major:         ## Version major
	npm version major && \
	$(MAKE) postVersion

minor:         ## Version minor
	npm version minor && \
	$(MAKE) postVersion

patch:         ## Version patch
	npm version patch && \
	$(MAKE) postVersion

postVersion:   ## Prepare version and push a new patch release on master and merge to develop
	@git checkout master && \
	npm version patch && \
	$(MAKE) pushWithTags && \
	$(MAKE) updateDevelop && \
	$(MAKE) pushWithTags

updateDevelop: ## Merge latest master into latest develop branch
	@git checkout master && \
	git pull && \
	git checkout develop && \
	git pull && \
	git merge master

pushWithTags:   ## Push release
	@git push && \
	git push --tags

releasePR:      ## Open PR URL
	@open https://github.com/maweeks/$(REPOSITORY_NAME)/compare/master...develop
```
