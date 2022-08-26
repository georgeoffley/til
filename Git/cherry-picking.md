# Cherry Picking 

This can be used to put commits into another PR. In our case we use it to add commits that we might need to solve issues into the release branch PR.

Commands

```bash
git fetch origin

git checkout <branch_we_want_to_add_commit_to>

git cherry-pick -x ##### # The commit hash of the merged PR

git push origin "$(git branch --show-current)"
```