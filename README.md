## 2020-02-24 Git basics

- `init`                : make current folder a git repository
- `status`              : see the status of the current repository.
- `add`                 : put file into the index ( staging area )
- `commit`              : commit the files from staging area
- `commit -m '"" `      : commit message directly
- ` diff`               : show difs:    `git diff` : show diffs with current file and commited file before . this is for a file not yed in the staging area
                            `git HEAD~1 README.md ` or `git diff bb957d3b9740e9ba09ae97dbcf4038e71daa0110 README.md`
- `git log --oneline`   : shows commits on one line per commit.
- `git diff --staged`   : show differences with commit and staging area
- `restore`             : get lat known  state back if you aded something to your file ( without git add ( or git commit ))
                        "   (use "git restore <file>..." to discard changes in working directory)"
                        this was same as `git checkout HEAD README.md`
- `git log --oneline --all --graph --decorate --stat` or 
- `git log --name-status` or 
- `git log --name-only` : show filenames
- `git add . `          : add everyhting starging fromthis directory.
- `git add --all`       : add everything.
- ` rebase`             : merge commits to let it look like it is one commit.


dus `git checkout HEAD test` is hetzelfde als ` git restore test `
de file is nog nit staged of commited.

git log --oneline --all --graph --decorate : usefull for when working with remotes.

- `checkout hash`       : restore entire folder to that point of time.
- `checkout hash file`  : restore file to that point of time.



als tie al gestaged was dan:
```
 git restore --staged test
 git restore test
```
dit kan dus ook met `git checkout 1ac3024 test`


met `git checkout 1ac3024 test` ga je terug in de tijd,
daarna kan je weer terug met git checkout HEAD README.md

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   README.md
```

versus

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)   --> update: dit was de oude message )

        new file:   admin/logging/cronjob-kibana-index-backups/Dockerfile
        new file:   admin/logging/cronjob-kibana-index-backups/Makefile
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob-kibana-backups-all-in-one.yml
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob.yml
        new file:   admin/logging/cronjob-kibana-index-backups/script/kibana_index_backups.sh
```
this is solved wth upgrading git:
        ```

        2052  sudo add-apt-repository -y ppa:git-core/ppa
        2053  sudo apt-get update
        2054  sudo apt-get install git -y
```
Now the output on rm-kubernetes git status is:
```
 gs
On branch develop
Your branch is up to date with 'origin/develop'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   admin/logging/cronjob-kibana-index-backups/Dockerfile
        new file:   admin/logging/cronjob-kibana-index-backups/Makefile
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob-kibana-backups-all-in-one.yml
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob.yml
        new file:   admin/logging/cronjob-kibana-index-backups/script/kibana_index_backups.sh
```


-- `pull` : is autmatically doing a fetch and a merge
            a fetch is only showin gthe differences




play with older versions of file test:
```
  git log test
   git checkout bb957d3b9740e9ba09ae97dbcf4038e71daa0110  test
   git log test
   git checkout b3b2190837587baec91d708d43c780c322455aa4 test
 ``
