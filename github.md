# Set non empty local dir to git repo

## Set local dir as git repo:
```sh
git init
git add .
git commit -m "first commit"
```

## Create remote repo on Github profile

Go to github.com, click new on your profile.

## Link local repo to remote repo

```sh
git remote add origin <URL>
# If remote repo isn't empty merging remote files to local files (Mandatory !)
# git pull origin <branch(main or master)> --allow-unrelated-histories
# else create main branch
git branch -M main
git push -u origin main
```
