#Cheat Sheet for Git
Source: [https://github.com/luisbg/git-cheat-sheet](https://github.com/luisbg/git-cheat-sheet)

Command | Description
--- | ---
git add '*.txt' | Add only certain files
git add . | Add all modified files to be commited
git add [file] | Snapshots the file in preparation for versioning
git add –patch filename.x (or -p for short) | Snapshot only chunks of a file
git branch -D [branch] | Hard branch delete, will not complain
git branch -a | See the full list of local and remote branches
git branch -d [branch] | Deletes the specified branch
git branch -m <oldname> <newname> | Rename a branch
git branch [branch-name] | Create a new branch
git branch | Lists all local branches in the current directory
git checkout -b <name> <remote>/<branch> | Switches to a remote branch
git checkout [branch-name] | Switches to the specified branch and updates the working directory
git checkout [filename] | Return file to it's previous version, if it hasn’t been staged yet
git clone [url] | Downloads a project nd its entire version history
git commit -m "[descriptive message]" | Records file snapshots permanently in version history
git commit –amend | Changing the history, of the HEAD commit
git commit | Record changes to git. Default editor will open for a commit message
git config –global color.ui auto | Enables helpful colorization of command line output
git config –global core.editor [editor] | Which editor to use when commit and tag that lets you edit messages
git config –global diff.tool [tool] | Specify which command to invoke as the specified tool for git difftool
git config –global push.default current | Update a branch with the same name as current branch if no refspec is given
git config –global user.email "[email address]" | Sets the email you want attached to your commit transactions
git config –global user.name "[name]" | Sets the name you want attached to your commit transactions
git diff HEAD^ | Shows what has changed since the commit before the latest commit
git diff HEAD | Shows what has changed since the last commit.
git diff [branch] | Compare current branch to some other branch
git diff [file-branch]…[second-branch] | Shows content differences between two branches
git diff –no-commit-id –name-only –no-merges origin/master… | See only the file names that has changed in current branch
git diff –staged | Show what has been added to the index via git add but not yet committed
git diff –stat | See statistics on what files have changed and how
git difftool -d master.. | See only changes made in the current branch
git difftool -d | Same as diff, but opens changes via difftool that you have configured
git diff | Shows file differences not yet staged
git fetch -p | Update history of remote branches, you can fetch and purge
git fetch [bookmark] | Downloads all history from the repository bookmark
git init [project-name] | Creates a new local repository with the specified name
git log –author='Name' –after={1.week.ago} –pretty=oneline –abbrev-commit | See what the author has worked on in the last week
git log –follow [file] | Lists version history for a file, including renames
git log –no-merges master.. | See only changes in this branch
git log –pretty=format:"%h %s" –graph | Pretty commit view, you can customize it as much as you want
git log | Lists version history for the current branch
git ls-files –other –ignored –exclude-standard | Lists all ignored files in this project
git merge [bookmark]/[branch] | Combines bookmark's branch into current local branch
git merge [branch] | Combines the specified branch's history into the current branch
git merge –no–ff [branch] | Merge branch without fast forwarding
git mv [file-original] [file-renamed] | Changes the file name and prepares it for commit
git pull [remote] [branch] | Specify to pull a specific branch
git pull | Downloads bookmark history and incorporates changes
git push -u origin master | If a remote branch is not set up as an upstream, you can make it so
git push [remote] [branch] | Manually specify remote and branch to use every time
git push | Push current branch to remote branch
git remote -v | Detailed view of remote repos available
git remote add [remote] [url] | Add a new remote
git remote | See list of remote repos available
git reset [commit/tag] | Undoes all commits after [commit], preserving changes locally
git reset [file] | Unstages the file, but preserves its contents
git reset –hard [commit] | Discards all history and changes back to the specified commit
git reset | Unstage pending changes, the changes will still remain on file system
git rm [file] | Deletes the file from the working directory and stages the deletion
git rm [file] | Tell git not to track the file anymore
git rm –cached [file] | Removes the file from version control but preserves the file locally
git show [commit] | Outputs metadata and content changes of the specified commit
git stash drop | Discards the most recently stashed changeset
git stash list | Lists all stashed changesets
git stash pop | Restores the most recently stashed files
git stash | Temporarily stores all modified tracked files
git status -s | Short view of status
git status | Lists all new or modified files to be committed
