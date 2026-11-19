# Reusable repository starter

Create a GitHub template named `repo-template` in the OpenBoa organization. The template contains a stack-neutral initial tree and a maintainer-operated setup tool. A new repository should be usable on its first pull request and easy to verify after its settings change.

## Files and responsibilities

- The seed includes Git and editor defaults, minimal contribution and reporting guides, issue and PR forms, CODEOWNERS, a weekly GitHub Actions Dependabot group, and the tested read-only naming, workflow lint, whitespace and Gitleaks checks. Generic documentation explains how to initialize a generated repository. No application, package release, product name, product history, or default license belongs in the seed.
- Provide local initialization with explicit destination identity, description, default branch and an existing reviewer. Fill destination-specific README, CODEOWNERS and private reporting links. Validate inputs and preserve user-edited project files on repeat runs. Initialization only changes working-tree files and is reviewed in a normal PR.
- Keep trusted CI installers at an immutable reviewed revision. Do not introduce an organization-wide privileged workflow. Template updates reach existing repositories through explicit reviewed updates. The template itself has a documented update and release process.
- Check topic branch names and Conventional Commit-style PR titles. Permit any intermediate commit message. Verify the actual squash subject after a default-branch push. Account for GitHub's single initial commit when generating a new repository, without exempting later commits from naming checks.

## GitHub setup tool

- Support plan, apply and verify for an explicit target using an existing authenticated admin via the GitHub CLI. Plan and verify are read-only. Only apply may change the following settings: the merge strategy, merged-branch cleanup, squash title/body defaults, the named branch ruleset, supported read-only Actions permissions and SHA pins, and supported repository security features.
- Preserve unrelated settings and rulesets. Compare normalized responses before writing, reconcile after partial failures, identify missing permissions and unavailable plan features, and provide a nonzero verification result when required safeguards are absent. Never delete a repository or branch, change visibility, add collaborators, configure credentials, publish packages, or modify organization policy through the tool.
- Enable PR-only squash merges, linear history, resolved threads, denied force pushes and deletion, sensitive path ownership, and no bypasses. Require the two named checks from the verified GitHub Actions app only once there is live evidence from the expected workflow on a PR. Do not weaken an already enrolled required check.
- Keep the template source protected and enable the GitHub Template repository flag after its contents and live checks are verified. Distinguish template content from destination settings and from future language or release choices.

## Acceptance evidence

1. Identical second initialization and setup plans produce no changes, including against the two existing baseline repositories. A simulation covers a new repository, existing unrelated rules, unavailable features, missing producers and failed or partial requests.
2. A clean local generation with different destination information has the correct owner and reporting URL, retains no example product branding, and leaves existing user content intact.
3. Correct and invalid PR titles, branch types, Dependabot identity, freely named intermediate commits, initial generated history and final squash subjects have tests. Workflow lint and secret checks pass.
4. Verify template status, effective default-branch protections, public or private visibility as selected, PR CI and main CI. Report local generation tests separately from a live GitHub generation if creating a separate remote test repository is outside scope.
