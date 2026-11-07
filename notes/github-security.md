# Information Must Not Be Published

- Passwords
- Api keys
- GitHub personal access tokens
- .env file
- sensitive information
- personal information

# .gitignore
.gitignore file tell Git which files not to track.
```bash
# enviroment files
.env
# keys
*.key
```

we can verify if the file is ignored:
```bash
git check-ignore -v .env # check wheather specified file ignore by git
git ls-files .env # list files track by git and filter it with .env file
```

.gitignore does not remove files that Git already tracking.
to remove the file from Git's tracking:
```bash
git rm --cached FILE # remove the file from Git's tracking index. --cached protect the local copy
git status # make sure the file is staged for removal
git commit -m "MESSAGE" # commit the change
git status # verify the files is now untracked
```

if your secret files accidently be committed to local or pushed to GitHub,
you need to delete that files immediately by run:

accidently commit(local)
```bash
git reset --soft HEAD^ # move back to the parent of the current commit without touching the changes 
```
accidently push(GitHub)
```bash
git clone mirror LINK-TO-GITHUB-REPO FOLDER # backup the repo as bare repo. This done in different folder not in working directory
git filter-repo --path FILE --invert-paths # delete specified file from git history
git log --all --full-history -- FILE # check if the file is still exist
git push origin --force --all # forced push the cleaned history
```
