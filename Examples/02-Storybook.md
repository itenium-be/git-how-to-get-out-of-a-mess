02-Le-Advance
=============

Show graph in GitKraken & gmaster

PR with merge conflicts because the entire solutions branch
is going to be merged to master (without solutions):
https://github.com/itenium-be/Vue.js-Tutorial/pull/28


```bash
cd 02-Le-Advance

git branch -l
git checkout 2019-03-29-itenium
git log -2

# Those commits should've been made on master!
# Option 1: Cherry Picking
git checkout master
git cherry-pick 8e610a7102eecdf 7ba3bb197f44b5a3
git log -2 # Different SHA!

# Difference with rebase is that rebase also removes
# the commits
# git checkout 2019-03-29-itenium
# git reset --hard HEAD~2
```



```bash
# Let's make the existing solutions have a pretty history
# Option 2: Rebasing
git checkout 2019-03-29-itenium
git rebase -i e1d7907
git l
```
