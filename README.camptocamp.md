# Docsy

This theme is a customized version of Hugo [Docsy] theme with Camptocamp branding.

## Contributing

`upstream` branch must be a direct ancestor of the upstream main branch: it can be behind the upstream main branch, but cannot diverge from it. `main` branch must be ahead of `upstream` branch: each time `upstream` is synced with upstream, `main` has to be rebased.

### Prerequisites

Add upstream remote repository:

```
git remote add upstream git@github.com:google/docsy.git
git fetch upstream
```

### Rebasing on upstream main branch

```
git checkout upstream
git pull --tags --ff-only upstream main
git push
git checkout main
git rebase upstream
git push --force-with-lease
```

### Releasing a new version

```
git checkout <upstream-tag>
git cherry-pick upstream..main
git tag <upstream-tag>.c2c.<version>
git push origin <upstream-tag>.c2c.<version>
```

[Docsy]: https://www.docsy.dev
