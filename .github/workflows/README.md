# Automation/Workflow Project Explanation

## Naming Conventions for Versioning
This automation uses semantic versioning. See requirements for use below. 
### Branch Naming Standard
Branch names should use on of the following prefixs:
- patch/
- minor/
- major/
This will increment your projects version respectively.
### Commit Message Standard
*This only applies when commiting directly to the **main** branch*

Commits that are made to the main branch directly will need to have one of the following stirngs in the message:
- patch/
- minor/
- major/
This will increment your projects version respectively.

> If the standards above are not followed, it will default to a minor increment.

## Workflow Options
https://trunkbaseddevelopment.com/
### Trunk-Based
---
Once code is ready to be deployed Developer will commit directly to the **main** branch. Once a commit is pushed to the **main** branch the following will happen:
- code will be built
- code will be tested
- code will be linted
- code will be released with a git tag
- project version will be incremented based on commit message
- code will be deploed to heroku

### Scaled Trunk-Based
---
Developer will create a branch using the branch naming convention above. Then create a pull request into the **main** branch. On pull request creation and any commit to the feature branch the following will happen:
- code will be built
- code will be tested
- code will be linted

Once the Pull Request is approved and the build is successful then the Pull Request can be merged. Once the Pull Request is merged the following will happen:
- code will be built
- code will be tested
- code will be linted
- code will be released with a git tag
- project version will be incremented based on branch name
- code will be deploed to heroku
---
## Upcoming Feature updates to Automation
- Implement a manual deploy job for Heroku
- Create rollback function for bad deploys 
- Create multiple environment support
- Implement caching so checkout is not required for every job
- Consolidate dupliated code where possible
- Create a Service account for version increment so that main cant be committed to directly