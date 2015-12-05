#Cheat Sheet for Git
Source: [https://github.com/luisbg/git-cheat-sheet](https://github.com/luisbg/git-cheat-sheet)
##Configure
    // Sets the name you want attached to your commit transactions
    git config –global user.name "[name]"
    // Sets the email you want attached to your commit transactions
    git config –global user.email "[email address]"
    // Enables helpful colorization of command line output
    git config –global color.ui auto
    // Update a branch with the same name as current branch if no refspec is given
    git config –global push.default current
    // Which editor to use when commit and tag that lets you edit messages
    git config –global core.editor [editor]
    // Specify which command to invoke as the specified tool for git difftool
    git config –global diff.tool [tool]

##Create repositories
    // Creates a new local repository with the specified name
    git init [project-name]
    // Downloads a project nd its entire version history
    git clone [url]

##Make changes
    // Lists all new or modified files to be committed
    git status
    // Short view of status
    git status -s
    // Shows file differences not yet staged
    git diff
    // Snapshots the file in preparation for versioning
    git add [file]
    // Add all modified files to be commited
    git add .
    // Add only certain files
    git add '*.txt'
    // Snapshot only chunks of a file
    git add –patch filename.x (or -p for short)
    // Tell git not to track the file anymore
    git rm [file]
    // Show what has been added to the index via git add but not yet committed
    git diff –staged
    // Shows what has changed since the last commit.
    git diff HEAD
    // Shows what has changed since the commit before the latest commit
    git diff HEAD^
    // Compare current branch to some other branch
    git diff [branch]
    // Same as diff, but opens changes via difftool that you have configured
    git difftool -d
    // See only changes made in the current branch
    git difftool -d master..
    // See only the file names that has changed in current branch
    git diff –no-commit-id –name-only –no-merges origin/master…
    // See statistics on what files have changed and how
    git diff –stat
    // Unstages the file, but preserves its contents
    git reset [file]
    // Record changes to git. Default editor will open for a commit message
    git commit
    // Records file snapshots permanently in version history
    git commit -m "[descriptive message]"
    // Changing the history, of the HEAD commit
    git commit –amend

##Group changes
    // Lists all local branches in the current directory
    git branch
    // Create a new branch
    git branch [branch-name]
    // Switches to the specified branch and updates the working directory
    git checkout [branch-name]
    // Switches to a remote branch
    git checkout -b <name> <remote>/<branch>
    // Return file to it's previous version, if it hasn’t been staged yet
    git checkout [filename]
    // Combines the specified branch's history into the current branch
    git merge [branch]
    // Merge branch without fast forwarding
    git merge –no–ff [branch]
    // See the full list of local and remote branches
    git branch -a
    // Deletes the specified branch
    git branch -d [branch]
    // Hard branch delete, will not complain
    git branch -D [branch]
    // Rename a branch
    git branch -m <oldname> <newname>

##Refactor filenames
    // Deletes the file from the working directory and stages the deletion
    git rm [file]
    // Removes the file from version control but preserves the file locally
    git rm –cached [file]
    // Changes the file name and prepares it for commit
    git mv [file-original] [file-renamed]

##Suppress tracking
    // A text file named .gitignore suppresses accidental versioning of files and paths matching the specified patterns
    .gitignore
    // *.log
    // build/
    // temp-*
    // Lists all ignored files in this project
    git ls-files –other –ignored –exclude-standard

##Save fragments
    // Temporarily stores all modified tracked files
    git stash
    // Restores the most recently stashed files
    git stash pop
    // Lists all stashed changesets
    git stash list
    // Discards the most recently stashed changeset
    git stash drop

##Review history
    // Lists version history for the current branch
    git log
    // Lists version history for a file, including renames
    git log –follow [file]
    // Pretty commit view, you can customize it as much as you want
    git log –pretty=format:"%h %s" –graph
    // See what the author has worked on in the last week
    git log –author='Name' –after={1.week.ago} –pretty=oneline –abbrev-commit
    // See only changes in this branch
    git log –no-merges master..
    // Shows content differences between two branches
    git diff [file-branch]…[second-branch]
    // Outputs metadata and content changes of the specified commit
    git show [commit]

##Redo commits
    // Unstage pending changes, the changes will still remain on file system
    git reset
    // Undoes all commits after [commit], preserving changes locally
    git reset [commit/tag]
    // Discards all history and changes back to the specified commit
    git reset –hard [commit]

##Synchronize changes
    // Downloads all history from the repository bookmark
    git fetch [bookmark]
    // Update history of remote branches, you can fetch and purge
    git fetch -p
    // Combines bookmark's branch into current local branch
    git merge [bookmark]/[branch]
    // Push current branch to remote branch
    git push
    // Manually specify remote and branch to use every time
    git push [remote] [branch]
    // If a remote branch is not set up as an upstream, you can make it so
    git push -u origin master
    // Downloads bookmark history and incorporates changes
    git pull
    // Specify to pull a specific branch
    git pull [remote] [branch]
    // See list of remote repos available
    git remote
    // Detailed view of remote repos available
    git remote -v
    // Add a new remote
    git remote add [remote] [url]
