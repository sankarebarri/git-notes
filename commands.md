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