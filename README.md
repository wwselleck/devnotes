# Dev Notes

## Back End

- 📖 [**Designing Data-Intensive Applications**](https://dataintensive.net/) - Martin Kleppmann

### HTTP
- 📝 [HTTP Made Really Easy](https://www.jmarshall.com/easy/http/)
- 💭 [Difference between "Cache-Control: max-age=0" and "Cache-Control: no-cache"](http://stackoverflow.com/questions/1046966/whats-the-difference-between-cache-control-max-age-0-and-no-cache)

### Authn/Authz
- 📝 [An Introduction to OAuth 2](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

## Web Front-End
- [THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveintohtml5.info/storage.html)

## Linux
- 📝 [Linux System Administration Basics](https://www.linode.com/docs/tools-reference/basics/linux-system-administration-basics/)
- 📝 [How To Configure a Linux Service](https://www.digitalocean.com/community/tutorials/how-to-configure-a-linux-service-to-start-automatically-after-a-crash-or-reboot-part-1-practical-examples)

## Object Oriented Programming
- 📝 [Why getter and setter methods are evil](https://www.infoworld.com/article/2073723/why-getter-and-setter-methods-are-evil.html)

## Javascript
- 🎥 [What the heck is the event loop anyway? | Philip Roberts | JSConf EU](https://www.youtube.com/watch?v=8aGhZQkoFbQ)

### Legacy 
These articles aren't too relevant for today's JS, but were helpful at the time and still useful for historical learning.
- 📝 [Overwhelmed by Javascript Dependencies](http://blog.startifact.com/posts/overwhelmed-by-javascript-dependencies.html)

## Typescript
- 📖 [**Effective Typescript**](https://effectivetypescript.com/) - Dan Vanderkam

## C++
- 📝 [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines)

## Rust
- 📝 [Rust via its Core Values](http://designisrefactoring.com/2016/04/01/rust-via-its-core-values/)

## GraphQL
- 📝 [Demystifying the info Argument in GraphQL Resolvers](https://www.prisma.io/blog/graphql-server-basics-demystifying-the-info-argument-in-graphql-resolvers-6f26249f613a)

## Vim
- 💭 [What is the difference between the remap, noremap, nnoremap and vnoremap mapping commands in Vim?](https://stackoverflow.com/questions/3776117/what-is-the-difference-between-the-remap-noremap-nnoremap-and-vnoremap-mapping)
## Git
### Quick Reference
##### [git clone](http://git-scm.com/docs/git-clone)
+ Clone remote repository
  + `git clone <git url>`
    + e.g. `git clone https://github.com/wwselleck/weston-guides`
+ Clone remote repository into directory with custom name
  + `git clone <git url> [new name]`
    + e.g. `git clone https://github.com/wwselleck/weston-guides programming-guides`

##### [git add](http://git-scm.com/docs/git-add)
+ Add single file to index
  + `git add <file path>`
    + e.g. `git add src/hello-world.js`
+ Add all files in working tree to index
  + `git add -A`
+ Add all changed files in working tree to index, ignoring new files
  + `git add -u`

##### Branches
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

[How to reset/rollback to your last commit](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit)
