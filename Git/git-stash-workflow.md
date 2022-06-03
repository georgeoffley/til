# Git Stash Workflow

Using git stash is great for working on multiple branches with many other developers. It allows you to temporarily clear your current work on a branch without committing code which might not be ready to commit. 

This is useful as doing things like git pulls, git checkouts, or other git commands might be blocked if you have edited work on your current branch but have not committed the code.

So it goes like this:

1. Run `git stash save "note for stash"`
2. Then go do what you need to do, but when you come back to the branch and you want your chnages back you can run `git stash list` and you'll get something like the below:
```bash
goffley@Georges-MacBook-Pro-Fable fable-engine % git stash list
stash@{0}: On george/fab-2738-remove-beta-messaging-on-the-lottie: note1
stash@{1}: WIP on george/fab-2738-remove-beta-messaging-on-the-lottie: note2
```
3. Check out the list and when you locate the one you need run `git stash apply stash@{0}` to restore your work. The `stash@{0}` is the name of the stash you are applying.