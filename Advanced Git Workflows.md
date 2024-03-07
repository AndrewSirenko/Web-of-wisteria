Big thank you to the following resources: 
- BlueTufa's [dotfiles/git_notes.MD at main · BlueTufa/dotfiles](https://github.com/BlueTufa/dotfiles/blob/main/git_notes.MD)
## Remote repositories

List and add remotes

```shell
git remote -v
git remote add upstream <upstream repo>
```

## Cleanup Branches

Delete all branches that are already merged into master. (Replace `master` with `main` if necessary)

```shell
git branch -d $(git branch --merged=master | grep -v master)
```

Removes local remote branches based on your repository

```shell
git fetch --prune --all
```

## Git Diff

List filenames different between branches
```shell
git diff upstream/master origin/master --name-only
```

Generate a patch

```shell
git diff > my.patch

git diff upstream/master origin/master > my.patch
git apply my.patch
```

Diff staging area against local repository
```sh
git diff --staged
```

Diff changes in a specific filename between two identifiers
```sh
git diff 9fae85 HEAD -- README.md
```
## Save yourself

Reflog: `git reflog` will show the previous states of your repository. You can reset or checkout to a specific reflog commit or a certain amount of repo actions back. (e.g. `git reset HEAD@{3}` will reset your local git state to whatever was 3 git actions ago)

Reset local branch to some other branch (like upstream)
```shell
git reset --hard upstream/<branch name>
```
## Better Rebasing

Quick Squash of last 3 commits
```shell
git reset --soft HEAD~3 && git commit --edit -m'blah'
```

Fixups and autosquash 
```sh
git commit --fixup=<some-old-commit-id>
...

git rebase -i --autosquash
```

## Auto resolve repeat merge conflicts

[version control - What is git-rerere and how does it work? - Stack Overflow](https://stackoverflow.com/questions/49500943/what-is-git-rerere-and-how-does-it-work)
