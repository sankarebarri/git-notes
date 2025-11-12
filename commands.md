# Revert all your uncommitted changes back to the last pushed version

```bash
git restore .
git clean -fd # -f flag to actually delete the files, -d remove any untracked directories, not just files.
```

# Currently have uncommitted changes in current branch and switching to another branch would overwrite them.
## Temporarily stash them so you can restore them after switching:

```bash
git stash push -m "work in progress on docs-move-examples"
git switch docs-working-examples
```

## When you return to docs-move-examples, restore the stash:

```bash
git switch docs-move-examples
git stash pop
```

# Discard all uncommitted changes

```bash
git restore .
git clean -fd
```

## Switch and reset to the upstream version

```bash
git switch main
git reset --hard upstream/main
```

# Keeps your fork tidy and aligned with upstream.

```bash
git push --force-with-lease origin main
```

# branch
## view

```bash
git branch # local branch
git branch -r # remote branch
```

## delete

```bash
git branch -D <branch-name> # delete local branch
git push origin --delete <branch-name> # delete remote branch
```
## verify clean up

```bash
git fetch --prune
git branch -a
```

### Common workflow (what maintainers do too) after a PR is merged

```bash
git switch main
git fetch upstream
git reset --hard upstream/main
git branch -D docs-working-examples
git push origin --delete docs-working-examples
```