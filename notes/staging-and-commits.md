# Flow and Status
git status tells you the current branch and the condition of all files.
There are fews git status condition:
```text
Untracked # git sees a new file but never told to include it
Modified  # git tracks the files and see the changes from last commit
Staged/changes to be commited # selected to be in the next commit
Clean/nothing to commit # working directory match with latest commit
```

The flow of Git can be explain like this:
```text
working directory    ->    staging area    ->    repository history
  [edited files]        [selected changes]    [permanent commit records]
```
# Staging and Commit
command:
```bash
git status              # tell the condition of each file in current branch
git add FILE            # stages a specific file(ready to commit)
git commit -m "MESSAGE" # writes staged files to local git history
```

```bash
git diff          # show changes not yet staged
git diff --staged # show changes staged and will be commit
git log --oneline # display history. --oneline make each commit one compact line
```
# .gitignore
.gitignore is used to explicitly write the files that we never want git to
commit or push to remote branch or github. Usually used to store sensitive files.
this can just be create by run:
```bash
touch .gitignore
nano .gitignore  #will open .gitignore in the text editor
```
