# First line of this new README file
## 2020-02-24 Git basics

- `init`    : make current folder a git repository
- `status`  : see the status of the current repository.
- `add`     : put file into the index ( staging area )
- `commit`  : commit the files from staging area
- `commit -m '"" `: commit message directly
- ` diff`   : show difs:    `git diff` : show diffs with current file and commited file before . this is for a file not yed in the staging area
                            `git HEAD~1 README.md ` or `git diff bb957d3b9740e9ba09ae97dbcf4038e71daa0110 README.md`
- `git log --oneline` : shows commits on one line per commit.
- `git diff --staged` : show differences with commit and staging area
- `restore`: get lat known  state back if you aded something to your file ( without git add ( or git commit ))
            "   (use "git restore <file>..." to discard changes in working directory)"
            this was same as `git checkout HEAD README.md`

dus `git checkout HEAD test` is hetzelfde als ` git restore test `
de file is nog nit staged of commited.



als tie al gestaged was dan:
```
 git restore --staged test
 git restore test
```


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



