For this example we assumes a few things:
- link to GitHub repo is https://github.com/user/git-github-workflow-lab
- API_KEY=12345678
- start as folder git-github-workflow-lab/
- current branch is main
- Initially there is no .gitignore file

command:
```bash
git init
ls -a
```

expected output:
```text
. .. .git
```

command:
```bash
touch README.md
echo "this is README file" > README.md
git add README.md
git commit -m "add README file"
```

expected output:
```text
[main (root-commit) 1a2b3c4] add README file
 1 file changed, 1 insertions(+)
 create mode 100644 README.md
```

command:
```bash
git switch -c edit-readme
```

expected output:
```text
Switched to a new branch 'edit-readme'
```

command:
```bash
echo README.md "changed README" > README.md
git add README.md
git commit -m "change README"
```

expected output:
```text
[main 5e6f7a8] change README
 1 file changed, 1 insertion(+), 1 deletion(-)
```

command:
```bash
git switch main
cat README.md
```

expected output:
```text
this is README file
```

command:
```bash
git merge edit-readme
```

expected output:
```text
Updating 1a2b3c4..5e6f7a8
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

command:
```bash
cat README.md
```

expected output:
```text
changed README
```

# link local repo to github repo 
command:
```bash
git remote add origin https://github.com/user/git-github-workflow-lab
git push -u origin main
```

# Restore & Revert

command:
```bash
rm README.md
ls -a
```

expected output:
```text
. .. .git
```

command:
```bash
git restore README.md
ls
```

expected output:
```text
README.md
```

command:
```bash
touch .env
echo "API_KEY=12345678" > .env
git add .
git commit -m "accidently push .env"
git push
```

expected output:
```text
[main d73f2a1] accidently push .env
 1 file changed, 1 insertion(+)
```

if accidently commit and push .env file
command:
```bash
cd ..
git clone --mirror https://github.com/user/git-github-workflow-lab backup
cd backup
git filter-repo --path .env --invert-paths
git log --all --full-history -- .env
git push origin --force --all
git push origin --force --tag
cd ..
cd git-github-workflow-lab
git fetch origin
git reset --hard origin/main
```
this will remove .env file fromm all git commit's history and restore
the clean version of repo to both GitHub and local repo.
