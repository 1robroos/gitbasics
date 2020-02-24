# First line of this new README file
## 2020-02-24 Git basics

- `init`    : make current folder a git repository
- `status`  : see the status of the current repository.
- `add`     : put file into the index ( staging area )
- `commit`  : commit the files from staging area

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   README.md
```

versus

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   admin/logging/cronjob-kibana-index-backups/Dockerfile
        new file:   admin/logging/cronjob-kibana-index-backups/Makefile
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob-kibana-backups-all-in-one.yml
        new file:   admin/logging/cronjob-kibana-index-backups/deployment-cronjob.yml
        new file:   admin/logging/cronjob-kibana-index-backups/script/kibana_index_backups.sh
```

-- `pull` : is autmatically doing a fetch and a merge
            a fetch is only showin gthe differences
