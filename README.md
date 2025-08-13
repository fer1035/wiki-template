# \<Repository-Name>

\<Team-name> team documentation wiki source

---Remove this line and the contents below---

## CCoE-Wiki-Template

Template repository to create wiki source repositories.

## Steps

To create a new Wiki repository:

- Select this repository as the template.
- Customize the skeleton files once the new repository has been created using the standard Git workflow.
- Create the pipelines.
- Populate build pipeline variables:
    - GITHUB_USER
    - GITHUB_TOKEN
- Update branch rulesets (the required status check for the PR pipeline needs to be enabled after the pipeline has been run manually at least once ***after*** its initial creation).

### Suggested Branch Ruleset

- Name: SDLC
- Enforcement: Active
- Bypass: Repository admin (role)
- Target: Default (main)
- Rules:
    - [x] Restrict creations
    - [ ] Restrict updates
    - [x] Restrict deletions
    - [ ] Require linear history
    - [ ] Require merge queue
    - [ ] Require deployments to succeed
    - [ ] Require signed commits
    - [x] Require a pull request before merging
        - Required approvals
            - Specify number
        - [x] Dismiss stale pull request approvals when new commits are pushed
        - [x] Require review from Code Owners
        - [x] Require approval of the most recent reviewable push
        - [x] Require conversation resolution before merging
        - [ ] Request pull request review from Copilot
        - Allowed merge methods:
            - [x] Merge
            - [ ] Squash
            - [ ] Rebase
    - [x] Require status checks to pass
        - [x] Require branches to be up to date before merging
        - [ ] Do not require status checks on creation
        - Use ***if*** status checks are available
        - PR pipelines is a good candidate
            - Add checks (search for **pr**)
    - [x] Block force pushes
    - [ ] Require code scanning results
        - Use ***if*** code scanning is activated
- Restrictions
    - [ ] Restrict commit metadata
    - [ ] Restrict branch names
