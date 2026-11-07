# Branch
Branch is a named pointer to sequence of commits. main is a default
primary branch. we create another branch to test a new feature or try to
fix current feature safely and without risking to broke the main branch.
It can be create using this command:
```bash
git switch -c branch-name # -c make sure the branch be created first before switching
```
changes made to that branch will not affect the main branch unless
we merge it:
```bash
git switch main
git merge branch-name
```
this will merge both branches. Git may report the merge conflict if
two changes alter the same lines incompatibly.

# push to GitHub
before pushing your local branch to the github, make sure the branch name 
is match because github by default use branch named main.
```bash
git branch -m/-M main # rename the current branch to main
```

to push for the first time we need to create a bookmark that link the
local branch to the repository in github.
```bash
git remote add origin LINK # create the bookmark named origin
git push -u origin main    # push main branch using origin bookmark
                           # -u is to set default upstream
```

# pull request
pull request is done by creating another branch to fix a bug or add
new feature then push it to github repo. It then will be check or review
by the repo owner or few collaborator before being allow to be merge to
the main branch.
