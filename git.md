# Git
- 📝 [Git Flight Rules](https://github.com/k88hudson/git-flight-rules)
- 📝 [Understanding git for real by exploring the .git directory](https://www.daolf.com/posts/git-series-part-1/)
- 📝 [Git koans](https://stevelosh.com/blog/2013/04/git-koans/)

## [git clone](http://git-scm.com/docs/git-clone)
+ Clone remote repository
  + `git clone <git url>`
    + e.g. `git clone https://github.com/wwselleck/weston-guides`
+ Clone remote repository into directory with custom name
  + `git clone <git url> [new name]`
    + e.g. `git clone https://github.com/wwselleck/weston-guides programming-guides`

## [git add](http://git-scm.com/docs/git-add)
+ Add single file to index
  + `git add <file path>`
    + e.g. `git add src/hello-world.js`
+ Add all files in working tree to index
  + `git add -A`
+ Add all changed files in working tree to index, ignoring new files
  + `git add -u`

## Branches
+ Show branches and their commits
  + `git show-branch`<sup>[[0]](https://git-scm.com/docs/git-show-branch)</sup>
+ Show all local and remote branches
  + `git branch -a` <sup>[[0]](http://gitready.com/intermediate/2009/02/13/list-remote-branches.html)</sup>
+ Rename a local branch
  + `git branch -m <oldname> <newname>`<sup>[[0]](http://stackoverflow.com/questions/6591213/how-to-rename-the-local-branch)</sup>
    + e.g. `git branch -m feature/old-name feature/new-name`
    + If you are already on the branch you want to rename, this can be shortened to
      + `git branch -m <newname>`
+ Delete local branch
  + `git branch -d <branch name>` <sup>[source](http://makandracards.com/makandra/621-git-delete-a-branch-local-or-remote)</sup>
    + e.g. `git branch -d feature/add-navigation`
+ Delete remote branch
  + `git push origin --delete <branch name>` <sup>[source](http://stackoverflow.com/questions/2003505/delete-a-git-branch-both-locally-and-remotely)</sup>
    + e.g. `git push origin --delete feature/add-navigation`
+ Push local branch to remote
  + `git push --set-upstream origin <branch name>`
    + e.g. `git push --set-upstream origin feature/US14933-skeleton-cleanup`
## Rebasing
- Rebasing branch with amended history 
  - 💭 https://stackoverflow.com/questions/49242685/how-to-rebase-onto-branch-that-has-overwritten-history/49243225#49243225
  Read official rebase docs if confused https://git-scm.com/docs/git-rebase
  - Example
    - `git rebase --onto master <sha>`
where sha is the commit before all of the commits you want to keep

## Fixing the Past
- 💭 [How to reset/rollback to your last commit](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit)
