# This documents is dedicated to recording every weird thing that I have encountered when using git and github.

## I. How to resolve a conflict in a team project?
1. You must execute `fetch` and `merge` first before `commit` and `push`, otherwise you can see a conflict, especially when I keep working on the same file.
2. When there is a conflict, the `merge` command will tell you which of your files are conflicting with the incoming files.
3. You can resolve the conflicts by choosing a version of code. You can also manually change the code.
4. When resolving all conflicts, usually you can execute `git add .`, `git commit` and `git push` to upload your files to your origin (your own repo).
5. If you cannot push, you can run `git push -f` to force your push.
6. When you make a pull request to the upstream (team repo), conflicts can happen too. You can use the github interface to resolve the problem.
7. After your pull request is approved, and suash and merge, the record can look a bit unusual, including extra information, but it should be fine.
8. Just remember to run `fetch` and `merge` in advance and frequently to avoid this problem.


## What are the normal procedures of uploading files to the team repo?
1. Register the upstream
- `git remote -v` List the current configured remote repository.
- `git remote add upstream git@github.com:{team repo}.git` Specify a new remote upstream repository that will be synced with the fork.
- `git remote -v` List the current configured remote repository.
2. Merge changes from upstream:
- `git fetch upstream` Fetch the branches and their respective commits from the upstream repository.
- `git checkout master` Enter your fork's local master branch.
- `git merge upstream/master` Merge the changes from upstream/master into your local master branch. If your local branch didn't have any unique commits, Git will instead perform a 'fast-forward'.


## III. What can you do when you want to reverse a pushed commit to the github account?
1.  Run this command:
```
git revert {id / hash}
```
2. Since the reverted files will be stored in the commit area, you need to push again to your repo.


