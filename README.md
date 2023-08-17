# gha-trigger-ci

Trigger a Silverstripe CI workflow

For repositories on the Silverstripe account there are currently 3 different filenames that a CI workflow can be:
- ci.yml -- used for regular modules
- action-ci.yml -- used on gha-* repositories
- action-ci-self.yml -- used only on gha-action-ci

This action will find and trigger the appropriate CI workflow.

Note this is similarly named but distinct from [gha-dispatch-ci](https://github.com/silverstripe/gha-dispatch-ci) which 
is used on a schedule event to trigger a CI workflow on two different major versions of supported Silverstripe modules.

## Usage

**workflow.yml**
```yml
steps:
  - name: Trigger CI
    uses: silverstripe/gha-trigger-ci@v1
    with:
      branch: 4.13
```

### Inputs:

#### Branch
The branch to run the workflow on
`branch: pulls/4/my-branch`

#### Validate branch
Whether to validate if the branch exists via GitHub API. You may wish to disable this if the branch was only just created 
and the GitHub API hasn't caught up yet. Defaults is `true`
`validate-branch: false`
