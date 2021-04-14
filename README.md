

# Mobillium Git Guidelines

### Table of Contents

1. [Master & Develop Branches](#master-develop)
1. [Feature & Epic Branches](#feature-epic)
1. [Release & Bugfix Branches](#release-bugfix)
1. [Hotfix Branches](#hotfix)
1. [Commit Messages Template](#commit-messages-template)
1. [Summary](#summary)
1. [References](#references)


<a name="master-develop"></a>
## Master & Develop Branches

![](Images/master-develop.svg)

We have two main branches. These are `master` and `develop`.
* The `master` branch store the latest released codebase.
* The `develop` branch store the latest codebase.



<a name="feature-epic"></a>
## Feature & Epic Branches

![](Images/feature-epic.svg)

### Small Tasks
* Each new `small` `feature` should be created from `develop`.
* Branch name should be start with `feature/`, if you have `ISSUECODE` branch name should be end continue `ISSUECODE` and short task name(e.g. `feature/MBL-1234-short-task-name`) else branch name should be end with task name(e.g. `feature/short-task-name`).
* After the tests are completed and approved, they should be merged back to related `develop` branch.

### Large Tasks
* Each new `large` `feature` should be created from `develop`.
* Branch name should be start with `epic/` and end with task name.
* After the tests are completed and approved, they should be merged back to related `develop` branch.


* Sub-tasks of Large Tasks are should be created from `epic`.
* Branch name should be start with `feature/`, if you have `ISSUECODE` branch name should be continue with `ISSUECODE` and short task name(e.g. `feature/MBL-1234-short-task-name`) else branch name should be end with task name(e.g. `feature/short-task-name`).
* After the tests are completed and approved, they should be merged back to related `epic` branch.



<a name="release-bugfix"></a>
## Release & Bugfix Branches

![](Images/release-bugfix.svg)

> * ***Only `bugfix` can be made on the `release` branch.***
> * ***No new feature can be added to after branch created.***
> * ***If a new feature needs to be added, new release branch with increased version must be created.***

### Release Branches
* Each new `release` should be created from `develop`.
* Branch name should be start with `release/` and end with version number(e.g. `release/1.0.1`).
* After the new version is released, they should be merged to `master` and `develop` branches, and `master` should be tagged with an updated version numbers.


### Bugfix Branches
* Each new `bugfix` should be created from `release`.
* Branch name should be start with `bugfix/` and end with task name.
* After the tests are completed and approved, they should be merged back to related `release` branch.


<a name="hotfix"></a>
## Hotfix Branches

![](Images/hotfix.svg)


* The `hotfix` branches are used for quick bugfix on production releases.
* Each new `hotfix` should be created from `master`.
* Branch name should be start with `hotfix/` and end with version number(e.g. `hotfix/1.1.11`).
* After the fix is complete, they should be merged to `master` and `develop` branches, and `master` should be tagged with an updated version numbers.



<a name="commit-messages-template"></a>
## Commit Messages Template

Good commit messages that provide you useful information about what has changed and why. A well-crafted Git commit message is the best way to communicate context about a change to fellow developers (and indeed to their future selves). A diff will tell you what changed, but only the commit message can properly tell you why.

### Incorrect Commit Messages

![](Images/commit-messages-incorrect.svg)

### Correct Commit Messages

![](Images/commit-messages-correct.svg)

### Commit types

| Commit Type | Title                    | Description                                                                                                 |
| ----------- | ------------------------ | ----------------------------------------------------------------------------------------------------------- |
| `feat`      | Features                 | A new feature                                                                                               |
| `fix`       | Bug Fixes                | A bug Fix                                                                                                   |
| `docs`      | Documentation            | Documentation only changes                                                                                  |
| `style`     | Styles                   | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)      |
| `refactor`  | Code Refactoring         | A code change that neither fixes a bug nor adds a feature                                                   |
| `perf`      | Performance Improvements | A code change that improves performance                                                                     |
| `test`      | Tests                    | Adding missing tests or correcting existing tests                                                           |
| `build`     | Builds                   | Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm, Alamofire,)         |
| `ci`        | Continuous Integrations  | Changes to our CI configuration files and scripts (example scopes: SonarCloud, Bitrise) |
| `chore`     | Chores                   | Other changes that don't modify src or test files                                                           |
| `revert`    | Reverts                  | Reverts a previous commit                                                                                   |



<a name="summary"></a>
## Summary

![](Images/gitflow.svg)

The overall flow of Gitflow-M is:

1. A `develop` branch is created from `master`
2. `Epic` branches are created from `develop` for large tasks
2. for sub-tasks of large tasks `Feature` branches are created from `epic`
2. When a `epic` is complete it is merged into the `develop` branch
3. for small tasks `Feature` branches are created from `develop`
3. When a `feature` is complete it is merged into the `develop` branch
4. A `release` branch is created from `develop`
4. `Bugfix` branches are created from `release`
5. When the `release` branch is done it is merged into `develop` and `master`
6. If an issue in `master` is detected a `hotfix` branch is created from `master`
6. Once the `hotfix` is complete it is merged to both `develop` and `master`



<a name="references"></a>
## References

* [Atlassian Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
