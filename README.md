# Basic stuffs at work

## Git CLI
* Daily cycle of a progress update:
```
git checkout main_working_branch
git fetch
git pull
git checking your_working_branch
git merge main_working_branch
```

* Committing to a wrong branch:
```
git reset HEAD^ # do a git log and git status after, you'll realise
                # that we removed the last commit, but the changes are still
                # available to us
git stash save "saved-work" # you will save all your changes into a 'stash'
                            # you can retrieve this later
git checkout stage_adperform_v3
git stash list     # will tell you what "number" your "saved-work" is saved in
git stash apply 0  # I assume the work is saved in '0'. This will bring everything
                   # back
git add *;
git commit -m "...." # as before
```
* `git branch <name>` bases on your current branch by default.
* Why `-m` in `git commit -m "Message"`? M stands for message.
* 

## Linux Commands

* `grep -rn '<search keyword>' <dir>` Finding appearance location of keywords inside `dir`.
* `mysql <name> < <file>` Running a query file.
* `mysql <name> -e '<execution line>'` Running a fast query.

## Bash Scripts
* `chmod +x file.sh` Compile bash file
* `./file.sh` Running bash file
* Sample script of running all `sql` files in a directory, credit to Barry Wu:
```
#!/bin/sh
cd /opt/audio-cc/sql/up
for f in `ls *sql`
do
 read -p "Continue? (ctrl+c to quit)" yn;
 echo "Processing $f"
 mysql audiocc < $f
 # do something on $f
done
```
