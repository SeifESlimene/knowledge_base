# ==Useful Git Commands==

---

##### Git stores configuration options in three separate files, which lets you scope options to individual repositories (local), user (Global), or the entire system (system):

| Command                   | Scope | Description                       |
| ------------------------- | ----- | --------------------------------- |
| `/.git/config`   | Local | Repository-specific settings  |
| `/.gitconfig`  | global | User-specific settings. This is where options set with the --global flag are stored |
| `$(prefix)/etc/gitconfig`  | system | System-wide settings |

---

##### List Git Configuration For All Scopes:

| Command                   | Description                       |
| ------------------------- | --------------------------------- |
| `git config --local -l`   | List Git Configuration For Local  |
| `git config --global -l`  | List Git Configuration For Global |
| `git config --system -l`  | List Git Configuration For System |

---

##### Change Configuration In Files For All Scopes:
| Command                   | Scope                             |
| ------------------------- | --------------------------------- |
| `git config --local --edit`   | local  |
| `git config --global --edit`  | global |
| `git config --system --edit`  | system |

---

##### Changing Credentials In Local:
> `$ git config --local user.name <name>`

> `$ git config --local user.email <email>`

---

##### Some Aliases:
> `$ git config --local alias.<alias-name> <git-command>`

> `$ git config --local alias.st status`

> `$ git config --local alias.co checkout`

> `$ git config --local alias.br branch`

> `$ git config --local alias.up rebase`

> `$ git config --local alias.ci commit`

---

##### Sync A File With The Master Branch:
> `$ git checkout origin/master -- <file_location>`

---

##### List All Stashed Work:
> `$ git stash list`

---

##### Save Work:
> `$ git stash`

---

##### Unstash Saved Work:
> `$ git stash pop`

---

##### Show All Commits Starting By The Oldest One:
> `$ git log --reverse`

---

##### Git commit With Resolve Commit:
> `$ git commit -am "resolve conflict"`

---

##### Changing the most recent commit

> `$ git commit --amend -m "New and correct message"`

---

##### Remove last commit From Local and Remote Branch

> `$ git reset --hard 606dcf2630c60c7a02f0dd28ca985711388385cc`

PS: don't forget to stash/shelve all changes as this command remove all local changes without asking.

----

##### Showing commits made directly to a branch, ignoring merges

> `$ git log --no-merges --first-parent`

git stash save <name-of-stash>
git push https://username@github.com/username/repo
