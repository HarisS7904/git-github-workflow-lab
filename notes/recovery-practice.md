# Discard Uncommited Change
```bash
git diff # print changes of unstaged files
git restore FILE # restore the unstaged/modified files to latest commit version
```

# Discard While Preserve Change
```bash
git diff --staged # print changes of staged files
git restore --staged FILE # remove the file from that have been added to be staged
```

# Restore an Accidentally Deleted File
```bash
git status # print the status of current branch. Used to see restorable deleted files
git restore FILE # recover the file that have been deleted
```

# Undo a Commit
```bash
git log --oneline # print commit history in one line for each commit
git revert [HASH_COMMIT]/[HEAD] # revert the branch to the previous commit states
```
