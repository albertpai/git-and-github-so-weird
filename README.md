## Git and gitub are so weird!

Because they are sooooo weird, I write this document to record every weird problem that I have encountered so far.


### I. How to resolve a conflict when working with a team project?
1. You must execute `fetch` and `merge` first before running `commit` and `push`, otherwise you can see a conflict, especially when I keep working on the same file.
2. When there is a conflict, the `merge` command will tell you which of your files are conflicting with the incoming files.
3. You can resolve the conflicts by choosing a version of code. You can also manually change the code.
4. When resolving all conflicts, usually you can execute `git add .`, `git commit` and `git push` to upload your files to your origin (your own repo).
5. If you cannot push, you can run `git push -f` to force your push.
6. When you make a pull request to the upstream (team repo), conflicts can happen too. You can use the github interface to resolve the problem.
7. After your pull request is approved, and suash and merge, the record can look a bit unusual, including extra information, but it should be fine.
8. Just remember to run `fetch` and `merge` in advance and frequently to avoid this problem.


## II. What are the normal procedures to uploead files to a team repo?
1. Register the upstream
- Run `git remote -v`. List the current configured remote repository.
- Run `git remote add upstream git@github.com:{team repo}.git`. Specify a new remote upstream repository that will be synced with the fork.
- Run `git remote -v`. List the current configured remote repository.
- Check this [web page](https://help.github.com/articles/configuring-a-remote-for-a-fork/).
2. Merge changes from upstream:
- Run `git fetch upstream`. Fetch the branches and their respective commits from the upstream repository.
- Run `git checkout master`. Enter your fork's local master branch.
- Run `git merge upstream/master`. Merge the changes from upstream/master into your local master branch. If your local branch didn't have any unique commits, Git will instead perform a 'fast-forward'.
- Check this [web page](https://help.github.com/articles/syncing-a-fork/).


## III. How to revert a pushed commit in your github account?
1. If you push a commit that you did not mean to, you may want to revert a commit.
2. First of all, backup your correct files, because the files in your local folder would be entirely rewitten later.
2. Run this command: `git revert {id / hash}` to safely undo all the changes that have been made in an unwanted pushed commit.
3. Becasue the reverted files will be stored in the commit area, you must push everything again to your repo.
4. Finally, copy your latest files back to the local github folder.
5. Now, you can continue editing your files and upload to your repo again.
