# Scrolling Through Code As You Add To Commit

[Source](https://git-scm.com/docs/git-add)


In Git there is this awesome command for Git where you can actually look through the changed code one chunk at a time and decide whether or not you want to add it to a commit.

```bash
git add -p
```

The `-p` option lets you interactively look through the code. It essentially runs in interactive mode.

## Note
Please note that this command should only be run when you've made changes to files that are already tracked in Git. This will not work with brand-new files that have not been committed before.

#Git 
