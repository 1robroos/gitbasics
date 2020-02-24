# 2020-02-24 Git basics

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
                        So `git checkout HEAD test` is same as ` git restore test ` ( file not staged or commited)
- `git log --oneline --all --graph --decorate --stat` or 
- `git log --name-status` or 
- `git log --name-only` : show filenames
- `git add . `          : add everyhting starging fromthis directory.
- `git add --all`       : add everything.
- ` rebase`             : merge commits to let it look like it is one commit.
- `git log --oneline --all --graph --decorate` : usefull for when working with remotes.
- `checkout hash`       : restore entire folder to that point of time.
- `checkout hash file`  : restore file to that point of time.
- `pull`                : is autmatically doing a fetch and a merge
- `fetch`               :  a fetch is only showing the differences



When file is already staged:
```
 git restore --staged test
 git restore test
```
So also possible with something like `git checkout 1ac3024 test` 
with `git checkout 1ac3024 test` you'll go back in time ( and try some stuff )
You can come back to the current tim ewith `git checkout HEAD README.md`


difference : `rm --cached` and `git reset head` 
```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   README.md
```

versus some other repo names "k8s":

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)   --> update: this was with older git versions)

        new file:   admin/logging/cronjob-kibana-index-backups/Dockerfile
        new file:   admin/logging/cronjob-kibana-index-backups/Makefileh
```
this is solved with upgrading git:
        ```
          sudo add-apt-repository -y ppa:git-core/ppa
          sudo apt-get update
          sudo apt-get install git -y
        ```
Now the output on repo "k8s" status is:
```
git status
On branch develop
Your branch is up to date with 'origin/develop'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   admin/logging/cronjob-kibana-index-backups/Dockerfile
        new file:   admin/logging/cronjob-kibana-index-backups/Makefile
```


play with older versions of file test:
```
  git log test
   git checkout bb957d3b9740e9ba09ae97dbcf4038e71daa0110  test
   git log test
   git checkout b3b2190837587baec91d708d43c780c322455aa4 test
 ``


## add a remote
$ git remote add origin git@github.com:1robroos/gitbasics.git
(base) [rob@rob-Latitude-5590 gitbasics (⎈ |rroos@ekstest2.us-west-2.eksctl.io:kubernetes-dashboard)]$ git remote -v
origin  git@github.com:1robroos/gitbasics.git (fetch)
origin  git@github.com:1robroos/gitbasics.git (push)
