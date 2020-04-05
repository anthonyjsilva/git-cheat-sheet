<img src="./git-logo.png" alt="git logo" width="200px"/>

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

## Git Diff

_View file changes made that have not been staged_

- `git diff`
- `git diff --stat --color master..branchName`
- `git diff master..branchName`

## Git Commit

_Create file snapshots permanently in version history_

Make a commit even when your branch has no changes

- `git commit --allow-empty`

Update the existing commit message

- `git commit --amend`

## git log - _See commit history_

View each commit condensed into one line

- `git log --oneline`

View altered files for commits

- `git log --stat`

View full diff of each commit

- `git log -p`

View history of commits for specified file

- `git log <file>`

View difference in commits between two branches

- `git log --oneline master..some-feature`

View commits since HEAD diverged from master

- `git log master...`

OR

- `git log master...{branch other than HEAD}`

## Delete branch locally and remotely

- `git branch -D branch_name`
- `git push origin :branch_name`
- `git push origin --delete feature/login`

Rename branch locally

- `git branch -m old_branch new_branch`

Delete the old branch

- `git push origin :old_branch`

Push the new branch, set local branch to track the new remote

- `git push --set-upstream origin new_branch`

## default git push

https://www.atlassian.com/git/tutorials/syncing/git-push
git checkout master
git fetch origin master
git rebase -i origin/master

<!-- Squash commits, fix up commit messages etc. -->

git push origin master

## see what commits have been added to the upstream master

git log --oneline master..origin/master

## git log remote master

git log origin/master

## git pull behavior

https://stackoverflow.com/questions/19279937/how-do-i-configure-git-to-automatically-pull-from-current-branch-when-using-git

git config --global branch.autoSetupMerge always

## git push behavior

https://stackoverflow.com/questions/948354/default-behavior-of-git-push-without-a-branch-specified

https://stackoverflow.com/questions/14031970/git-push-current-branch-shortcut/20922141

git config --global push.default current
git config push.default current

Other options:

nothing : Do not push anything
matching : Push all matching branches
upstream/tracking : Push the current branch to whatever it is tracking
current : Push the current branch

## git feature branch workflow

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

## git rebase

- `git pull --rebase origin master`

- `git add file`
- `git rebase --continue`
- `git rebase --abort`

- `git push --set-upstream origin branchname`

## git reset remote

- `git checkout master`
- `git reset --hard e3f1e37`
- `git push --force origin master`

## git merge local branches

on branch-A:
- `git merge branch-B`

on branch-A:
- `git merge --squash branch-B`

## git rename local and remote branch

- `git branch -m new-name`
- `git push origin --delete the_remote_branch`
- `git push origin new_name`

## git reset

1) UNDO local file changes but NOT REMOVE your last commit
- `git reset --hard`

2) UNDO local file changes AND REMOVE your last commit
- `git reset --hard HEAD^`

3) KEEP local file changes and REMOVE ONLY your last commit
- `git reset --soft HEAD^`

## git stash

git stash list
git stash show
git stash show -p
git stash show -p stash@{1}

## git push

https://www.atlassian.com/git/tutorials/syncing/git-push
git push <remote> <branch>

<!-- push no matter what -->

git push <remote> --force

<!-- all branches -->

git push <remote> --all

<!-- push tags as well -->

git push <remote> --tags

_Force push to overrid any version history differences between local and remote_

- `git push --force origin master`

## git tag

show tags

- `git tag`

add tag

- `git tag -a 1.0.0 -m "new component"`
- `git tag -a 2.20.3 -m "putting the v in Version!"`

push tags to remote

- `git push origin <tag>`
- `git push --tags`

safer alternative to --tags

- `git push --follow-tags`

delete remote tag

- `git push --delete origin 1.4.0`

delete local tag:

- `git tag --delete 1.4.0`

both

- `git tag --delete 1.4.0;git push --delete origin 1.4.0`

delete remote branch

- `git push -d <remote_name> <branch_name>`

delete local branch

- `git branch -d <branch_name>`

## Setting your branch to exactly match the remote branch

git fetch origin
git reset --hard origin/master

## git abort merge

git merge --abort


## References

https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf

https://www.git-tower.com/blog/git-cheat-sheet

https://gist.github.com/hofmannsven/6814451

https://gist.github.com/carlessanagustin/31c654b502e1fce23afb

https://gist.github.com/davfre/8313299
