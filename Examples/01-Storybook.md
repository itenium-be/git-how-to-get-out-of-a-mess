01-Le-Basic
===========

The socks are back!

```bash
cd 01-Le-Basic

git log --color --abbrev-commit --graph --date=relative --pretty=format:'%C(magenta)%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cd)%C(bold blue)<%an>%Creset'

# Explain the graph
# + Show in GitKraken/gmaster

# Already working on the Cart?
git stash pop # if working dir is clean
git diff
git stash save "WIP for Cart"
git stash list

# Start the "manual rebase"
git reset 676aaca
git diff

git add .gitignore
git commit -m"Patrick: Ignore webstorm settings"

git add README.md
git commit -m"Wouter: change git remote"

# Add Patch
git show f31629d # Patrick: Show selected variant
git show b8197fb #  Build error: fix linting issue

git add --patch # ATTN: Can also --patch when stashing
# Do explain the different options and manual edit
git diff
git diff --cached
git commit -m"Patrick: Show selected variant"

git commit -am"Build error: fax linting issue"

git l
git l --all
# Also show in Kraken

# Oops: Incorrect commit message!
git commit --amend -m"Build error: fix linting issue"

# Oh no! Also linting issue in Header.tsx!
# **Fix manually**
# Let's not create a separate commit for this:
git add react-socks/src/components/Header.tsx
git commit --amend

# If decided this is not a good idea after all
git reset --hard origin/master

# Or, to formalize
# Attention to dangers for downstream users!
git push origin master --force
# To rollback the force push:
# Find the git sha in the reflog
git reflog
# And restore
git reset --hard SHA
git push origin master --force

# Continue work on the Stash
git stash pop # Also: apply
```

Open `git-how-to-fix-a-mess.png` and explain what we've covered so far.

```bash
# Flatten merges
git checkout -b feature/cart
git commit -am"Cart implementation"

git po; git open;
# Create & merge PR for the Cart implementation

git checkout master
git pull
git l4
git rebase origin/feature/cart
git l4

# Could also: git pull --rebase
```
