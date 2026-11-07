# What is Git & Github
Git is designed to track the changes in source code files over time. It will
store all commit history, pull request, merge request etc. It can also be
use to create another branch to test a feature before decide to merge it
or otherwise.

GitHub is a website that used to host remote copies of Git repositories.
Most people use it to deploy their project to share their build or to
collaborate with others.

# Initialize Git
At first, your local folder just a regular normal folder.
To turn your local folder into a repository you just need to run:
```bash
git init
```
This will create .git file in that folder which will track your current folder.

> [!WARNING]
> NO files will be automatically track unless you explecitly defined it.

