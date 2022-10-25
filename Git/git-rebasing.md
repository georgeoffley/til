# Git Rebasing

Sometimes you need to move changes out of or into a branch. One way to do that is with `git rebase`.

Commands:

```bash
# go to develop
git checkout develop
# make develop latest
git pull origin develop
# go to your brnach
git checkout <branch_name>
# rebase on develop
git rebase develop
```

#Git 