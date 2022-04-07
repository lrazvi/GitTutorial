#Git Tutorial 
_For MacOS_

If you are not sure whether or not you have git installed you can do the following command in your terminal:
` git --version`

If you don't have it installed, it will prompt you to install it.

__Getting a Repository__
_Initializing_
Initializing creates a new Git repository. It can convert an existing, unversioned project to a Git repository or initialize a new, empty repository.

To initialize a repository in an existing directory, first go to the project's directory
`$ cd /Users/user/projectdirectory`
and then type
`$ git init`

_Cloning_
Cloning a repository targets an existing repository and create a clone, or copy of the target repository.

To clone an existing repository, enter the command:
`$ git clone <url>`

And to clone a repository into a specific directory enter
`$ git clone <url> projectdirectory`

___
Files in your working directory are either tracked or untracked, with tracked files being the files that Git knows about. Tracked files can be unmodified, modified, or staged.

_Staging_
A staging step in git allows you to continue making changes to the working directory and allows you to record changes in small commits.

_Commit_
Commits can be thought of as snapshots or milestones along the timeline of a Git project.

Untracked files are everything else in your working directory that have not been staged.

1. Untracked files get staged
2. Staged files get committed and become unmodified
3. Unmodified files become modified
4. Modified files get staged
5. Steps 2-4 are repeated (until there is a new untracked file to stage)

The status of your files can be checked with the command
`$ git status`

The `git add` command is multipurposed and can be used to track new files and stage modified files
1. Track new file
    `$ git add filename` 
2. Modify file
3. Stage file (double check status)
   `$ git add filename` 
4. Stage latest version of file (repeat step 3)
5. Commit
   `$ git commit`

__Branching__
Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes.

To create a branch run
`$ git branch newbranch`
And to check which branch you are currently on, run
`$ git log --oneline --decorate`
To switch to another existing branch (which also moves the Head to that branch), run
`$ git checkout otherbranch`

With every commit made, the Head of the branch will move forward, but if the branches were switched, the master branch will keep pointing at the first commit you were on.

To switch back to the master branch:
`$ git checkout master`
- Here the head switches back to the master branch
- It also reverts the files in your working directory back to the snapshot that master points to. 
- This also means any changes you make from now on will diverge from an older version of the project, basically allowing you to go back from the work you did in the branch you were working in and branch off in a new direction

A shortcut for making a new branch and switching to it at the same time is
`$ git checkout -b otherbranch`

You can delete a branch with the command
`$ git branch -d branchname`

__Merging__
Git merging combines sequences of commits into one unified history of commits.

To merge two branches, you have to check and switch to which branch you want to merge into and run the following command Ex: if you want to merge newbranch into the master branch
```
$ git checkout master
Switched to branch 'master'
$ git merge iss53
```
Git creates a new snapshot as well as a new commit that points to it, also referred to as a merge commit and is special in that it has more than one parent.
