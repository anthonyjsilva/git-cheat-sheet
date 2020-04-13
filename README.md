<img src="./git-logo.png" alt="git logo" width="200px"/>
<!-- ADD my own logo??? -->

# Git Cheat Sheet

A simplified summary of some of the most important git commands.

> _💪 Git good at git! 💪_

## Profile

_Configure your git profile_

Set your username / email for every git repo (repository) on your computer

- `git config --global user.name yourName`
- `git config --global user.email yourEmail`

Set your username / email only for the current git repo

- `git config user.name yourName`
- `git config user.name yourEmail`

See your git config

- `git config --list`

<!-- set editor as sublime -->
<!-- editor = subl -n -w -->

## Setup

_First time setup stuff_

Setup the current directory to be a git repo

- `git init`

Download an existing repo, including all of the files, branches, and commits

- `git clone repoURL`

## Remote

_View and / or change what remote repo the current local repo is connected to_

See the names of your connected remote repos

- `git remote`

See the names and exact URLs of your connected remote repos

- `git remote -v`

Change a URL of one of your connected remote repos

- `git remote set-url origin newRepoURL`

## Changes

_View file changes made that have not been staged with `git add`_

- `git diff`

Show the difference between two branches

- `git diff master..anotherBranchName`

With color

- `git diff --stat --color master..branchName`

## Saving

_Saves current changes into git history_

- `git commit fileToSave`

Make a commit even when your branch has no changes

- `git commit --allow-empty`

Rewrite a previous commit message

- `git commit --amend`

## History

_See git commit history_

View each commit condensed into one line

- `git log --oneline`

View altered files for commits

- `git log --stat`

View full diff of each commit

- `git log -p`

View history of commits for specified file

- `git log fileName`

View difference in commits between two branches

- `git log --oneline master..someOtherBranchName`

View commits since HEAD diverged from master

- `git log master...`

OR

- `git log master...someBranchOtherThanHEAD`

## Delete branch

Delete a branch locally and remotely

- `git branch -D branchName`
- `git push origin :branchName`
- `git push origin --delete branchName`

Rename branch locally

- `git branch -m oldBranchName newBranchName`

Delete the old branch

- `git push origin :oldBranchName`

Push the new branch, set local branch to track the new remote

- `git push --set-upstream origin new_branch`

## Rebasing

- `git pull --rebase origin master`

- `git add file`
- `git rebase --continue`
- `git rebase --abort`

- `git push --set-upstream origin branchname`

## Merging branches

On branchA

- `git merge branchB`

On branchA

- `git merge --squash branchB`

Abort

- `git merge --abort`

## Rename local and remote branch

- `git branch -m newBranchName`
- `git push origin --delete oldBranchName`
- `git push origin newBranchName`

## Resetting

1. UNDO local file changes but NOT REMOVE your last commit

- `git reset --hard`

2. UNDO local file changes AND REMOVE your last commit

- `git reset --hard HEAD^`

3. KEEP local file changes and REMOVE ONLY your last commit

- `git reset --soft HEAD^`

## Git pull behavior

https://stackoverflow.com/questions/19279937/how-do-i-configure-git-to-automatically-pull-from-current-branch-when-using-git

- `git config --global branch.autoSetupMerge always`

## Git push behavior

https://stackoverflow.com/questions/948354/default-behavior-of-git-push-without-a-branch-specified

https://stackoverflow.com/questions/14031970/git-push-current-branch-shortcut/20922141

- `git config --global push.default current`
- `git config push.default current`

## Pushing

https://www.atlassian.com/git/tutorials/syncing/git-push

- `git push <remote> <branch>`

Push no matter what

- `git push <remote> --force`

Push all branches

- `git push <remote> --all`

Push tags as well

- `git push <remote> --tags`

Force push to override any version history differences between local and remote

- `git push --force origin master`

## Tags

Show tags

- `git tag`

Add a tag

- `git tag -a 1.0.0 -m "new component"`
- `git tag -a 2.20.3 -m "putting the v in Version!"`

Push tags to remote

- `git push origin <tag>`
- `git push --tags`

Safer alternative to --tags

- `git push --follow-tags`

Delete a remote tag

- `git push --delete origin 1.4.0`

Delete a local tag

- `git tag --delete 1.4.0`

Delte a remote and local tag

- `git tag --delete 1.4.0; git push --delete origin 1.4.0`

Delete a remote branch

- `git push -d <remote_name> <branch_name>`

Delete a local branch

- `git branch -d <branch_name>`

## Force local branch to match remote branch

- `git fetch origin`
- `git reset --hard origin/master`

<!-- Move this somewhere else? -->

## Git feature branch workflow

https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow

- Start with the master branch
  git checkout master
  git fetch origin
  git reset --hard origin/master

- Create a new-branch
  git checkout -b new-feature

- Update, add, commit, and push changes
  git status
  git add <some-file>
  git commit

- Push feature branch to remote
  git push -u origin new-feature

- Resolve feedback, Merge your pull request

## References

- https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf

- https://www.git-tower.com/blog/git-cheat-sheet

- https://gist.github.com/hofmannsven/6814451

- https://gist.github.com/carlessanagustin/31c654b502e1fce23afb

- https://gist.github.com/davfre/8313299

- https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf

**Hope this helped!**