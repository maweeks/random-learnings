# TeamCity

## Example project

From development to deploy below is an example of how to set up your TeamCity jobs. This example assumes that your project needs to build for each environment that it needs to be deployed in.

- PR build - an automatically triggered build to run automatically against master, develop and any pull request branches and the ability to manually trigger the build for feature branches.
- Test deployment - a manually triggered build that can run with
- Test production deployment (_optional_) - a manually triggered build that can only run using tags that exist on master.
- Production deployment - a manually triggered build that can only run using tags that exist on master.

### Initial set up

#### Tips

- Use a template to reduce / reuse settings to easily ensure all builds are the same where intended.
- Enable Version configuration and set the VCS root to the repository for the current project - this will keep the build configuration and application in sync, as well as tracking changes making debugging issues with deployments significantly easier.

#### Project set up

#### Template set up

### PR build

Allow the template build on branches, pull requests and tags. VCS trigger for PR branches. Do not deploy the project after building.

### Test deployment

Allow the deployment of any branch using the build template.

### Production deployment

Restrict the deployment template to only run using tags that exist on the master branch. The optional test production deployment would use the same set up as below pointing at a different environment.

## Example project kotlin

There is an example project with this set up that you can find [here](.).

## TeamCity active branch age properties

```bash
teamcity.activeBuildBranch.age.hours
teamcity.activeVcsBranch.age.days
```
