
# GitFlow Branching Strategy - Practical Example

This document explains the GitFlow branching strategy with a practical example involving `dev`, `test`, and `prod` environments. It covers feature development, testing, production release, and hotfix handling.

## Branch Setup
```
git init

git checkout -b main       # Production-ready code
git checkout -b develop    # Integration branch for features
git checkout -b test       # For QA/staging
git checkout -b prod       # For production deployment
```
---

## Feature Development

```
# Create a feature branch from develop
 git checkout -b feature/login-page develop

# Make changes, then commit
 git add .
 git commit -m "Add login page feature"

# Merge feature into develop
git checkout develop
git merge feature/login-page
```
---

## Testing Phase

```
# Promote code from develop to test
git checkout test
git merge develop

# Run QA tests, fix bugs if needed
# Commit any fixes directly to test or backport to develop
```
---

## Production Release

```
# Promote tested code to prod
git checkout prod
git merge test

# Tag the release
git tag -a v1.0.0 -m "Release version 1.0.0"

# Push to remote
git push origin prod --tags
```
---

## Hotfix Example

```
# Create hotfix branch from prod
git checkout -b hotfix/login-bug prod

# Fix the bug, then commit
git add .
git commit -m "Fix login bug"

# Merge hotfix into prod and develop
git checkout prod
git merge hotfix/login-bug

git checkout develop
git merge hotfix/login-bug
```

---

This document illustrates a standard industry method to manage different environments in GitFlow.
