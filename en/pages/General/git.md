# Git

## Undoing Changes
The following are various commands to be used to undo changes in a number of different scenarios, including prior to committing, before tracking, after commit, and after pushing to the server.
<br/>

| Command | Explanation |
| --- | --- |
| `$ git revert --no-edit --no-commit <commit>` | stage a revert of all file changes from commit. |
| `$ git reset HEAD` | unstage all staged changes. |
| `$ git stage <file-to-revert>` | stage the changes that will revert only this one file. Repeat to include additional files. |
| `$ git commit -m "Reverting changes…"` | commit the staged changes to the local repo. |
| `$ git reset --hard HEAD` | undo all uncommitted changes. |
| `$ git push` | upload commit to the server. |
| `$ git clean -fd` | reset local untracked files |
| `$ git revert -m 1 <commit>` | Revert branch merge |


## Deleting Branches

| Command | Explanation |
| --- | --- |
| `$ git branch -D <branch>` | delete a local branch (with force option) |
| `$ git push origin --delete <branch>` | delete a remote branch |

## Create Integration Branch

| Command | Explanation |
| --- | --- |
| `$ git checkout master` | switch to the branch from which you intend to branch.  (master in this case) |
| `$ git pull` | make sure you have the latest commits by pulling. |
| `$ git checkout -b integration/BB-{epic#}-shortname` | create local branch |
| `$ git push -u origin integration/BB-{epic#}-shortname` | push local branch to the server and make the server the origin |

## Undo Local Changes

| Command | Explanation |
| --- | --- |
| `$ git checkout -- <file-to-undo>` | undo pending changes to a local file |


## Git Tagging
https://git-scm.com/book/en/v2/Git-Basics-Tagging


## Delete a Local Commit

| Command | Explanation |
| --- | --- |
| ``$ git reset --hard HEAD~1`` | delete the last commit |
| `$ git reset --hard <commit-id>` | go back to a specific commit in the history (discarding everything after it) |
| `$ git push origin HEAD --force` |  force push to get rid of a commit that was previously pushed (start with one of the above commands) be aware that this may not be a good idea if others have pulled the changes… when they push next those changes will be back.  Better, in that case, to simply revert and commit mirror changes to undo them. |


## Move the latest commit from one branch to another

| Command | Explanation |
| --- | --- |
| `$ git checkout <destination_branch>` | switch to the branch you want to move the commit to. |
| `$ git cherry-pick <source_branch>` | copy the latest commit from the source brach. |
| `$ git checkout <source_branch>` | switch back to the source branch |
| `$ git reset --hard HEAD^` | reset the source branch to 1 commit back from where you currently are. This effectively deletes that commit. |


## Stashing

| Command | Explanation |
| --- | --- |
| `$ git stash` | stash current pending changes |
| `$ git stash pop` | pop the top stash and reapply the changes |
| `$ git stash apply` | Reapply the changes of a stash without removing the stash itself. |
| `$ git stash apply stash@{n}` | Apply a specific stash that isn't necessarily at the top of the stack where 'n' is the stash number. |
| `$ git stash drop` | remove the top stash from the stack |

## List Branches That Have a Commit

| Command | Explanation |
| --- | --- |
| `$ git branch --contains <commit>` | This will list all branches where the given commit has been merged. |


## Switch origin URL
| Command | Explanation |
| --- | --- |
| `$ git remote set-url origin <new url>` | Use this to switch from HTTPS to SSH urls or visa versa. |
