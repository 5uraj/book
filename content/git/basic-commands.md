# Basic Commands

## git init

**git init **command used to initialize a empty git repository or reinitialize existing repository.

It will create **.git **folder into your working directory with some other folders and file like branches, hooks, objects, refs etc. An initial HEAD file refer the HEAD of the master branch is created.

`git init`

To create new repository, follow this 3 step: \[ in below example we create repository with name **example-git **\]

**Example:**

```
First you need to create folder into your local machine for git repository.

$ mkdir example-git

Change your working directory as new repository folder \[ example-git \]

$ cd example-git

Execute \*\*git init\*\* to create or initialize git repository

$ git init
```

See: [http://git-scm.com/docs/git-init](http://git-scm.com/docs/git-init)

## git clone

If you want to work with existing repository then you need to clone your existing repository into your local machine.

For clone repository into your local directory you need to use this command.

`git clone <repository url>`

**Example:**

```
To clone wpveda book repo into your local machine

$ git clone https://github.com/wpveda/book.git
```

```
To clone wpveda book repo into custom folder

$ git clone git@github.com:wpveda/book.git FOLDER-NAME
```

```
To clone specific branch from wpveda book repo

$ git clone git@github.com:wpveda/book.git -b BRANCH-NAME
```

See: [http://git-scm.com/docs/git-clone](http://git-scm.com/docs/git-clone)

## git status

This command shows status of current repository.

`git status`

Status contains list of files which have differences between the working tree and the index file, files which are not tracked by git. It's also show difference of local commit and remote commit so you can know how many commit are not push into remote branch.

**Example:**

```
To know status of \*\*example-git\*\* repository execute below command

$ git status
```

See: [http://git-scm.com/docs/git-status](http://git-scm.com/docs/git-status)

## git fetch

Fetch command use to fetch object and refs from remote or any other repository.

`git fetch [option] [remote] [branch]`

This command also fetch branches or tags from more then one repository with the object for that histories. by default it will use origin remote.

**Example:**

```
To fetch all branch or tag of origin remote
$ git fetch

To fetch all branch or tag of all configured remote
$ git fetch --all

To fetch master branch of origin remote
$ git fetch origin master
```

See: [http://git-scm.com/docs/git-fetch](http://git-scm.com/docs/git-fetch)

## git pull

To fetch change form remote or other repository and integrate with repository or local branch git provides **git pull** command.

`git pull [option] [remote] [branch]`

Git runs **git fetch** with given parameter and after that it will runs git merge to merge retrieved branch changes into current branch.

**Options:**

* **--rebase**: its will run git rebase after git fetch instead of git commit.

* **--no-commit**: with this option, it's perform git merge without affect merge fail and autocommit.

* **--force or -f**: it will force to fetch changes from remote and merge it with current branch.

**Note:** **--rebase **is more preferable to use with git pull, please refer given link for better idea.

See: [https://www.atlassian.com/git/tutorials/merging-vs-rebasing/](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/)

**Example:**

```
Update your current branch with remote branches for the repository you clone
$ git pull
  OR
$ git pull origin

Update current branch with remote master branch
$ git pull origin master

If any comment deleted from remote and not update in local than your local branch is ahead of remote branch.
in above case simple **git pull** not working you need to using git pull with --force option
$ git pull --force origin master
```

See: [http://git-scm.com/docs/git-pull](http://git-scm.com/docs/git-pull)

## git push

This command is logically opposite of git pull. This command used to update remote branch with local changes.

`git push [option] [remote] [branch]`

If remote is not specified then it will used origin. you can also specified pre-push hook. It will run before every push action.

**Options:**

* **--all**: its will push all branch of specified remote

* **--force or -f**: command refuses to update a remote commit that is not an ancestor of the local commit used to overwrite it.**--force**option force to push all commit.

* **-\[no-\]verify**: Toggle the pre-push hook.**-verify **used to prevent the push and **-no-verify **used to bypassed pre-push hook completely.

**Example:**

```
Update your remote [ origin ] branch with current branch for the repository you clone
$ git push
    or
$ git push origin

Update all local branches with appropriate remote branches
$ git push --all

Update remote branch which is ref to the master branch with current branch. if ref not found it will create new branch
$ git push origin master

To push current branch to the same name on remote branch.
$ git push origin HEAD
```

See: [http://git-scm.com/docs/git-push](http://git-scm.com/docs/git-push)

## git checkout

This command user to checkout branch or create new branch.

`git checkout [option] [branch]`

**Options:**

* **-b**: option used to create new branch

* **-B**: option used to create new branch and if exist then reset it to start point

* **-f**: it will force to change branch if index or the working tree differs form the HEAD \[ uncomited changes \]

**Example:**

```
To checkout or switch to live branch
$ git checkout live

To create new branch with name "stable"
$ git checkout -b stable
```

See: [http://git-scm.com/docs/git-checkout](http://git-scm.com/docs/git-checkout)

## git stash

This command used to stash the changes in a local machine. It will record your current state and clean working directory.

`git stash`

`git stash` is equivalent to `git stash save`

**Example:**

```
$ git stash
    or
$ git stash save

To restore change from stash to current working directory
$ git stash apply

To inspect stash change
$ git stash show
```

See: [http://git-scm.com/docs/git-stash](http://git-scm.com/docs/git-stash)

## git log

This command is used to show commit logs in the current branch.

`git log`

See: [http://git-scm.com/docs/git-log](http://git-scm.com/docs/git-log)

## git revert

This command is used to record some new commits to reverse the effect of some earlier commits \(often only a faulty one\).

`git revert [--[no-]edit] [-n] [-m parent-number] [-s] [-S[<keyid>]] <commit>`

**Example:**

```
Revert the changes specified by the fourth last commit in HEAD and create a new commit with the reverted changes.
$ git revert HEAD~3

Revert the changes done by commits from the fifth last commit in master (included) to the third last commit in master (included), but do not create any commit with the reverted changes. The revert only modifies the working tree and the index.
$ git revert -n master~5..master~2

Revert specific commit using commit ID
$ git revert <commit-id>
```

See: [http://git-scm.com/docs/git-revert](http://git-scm.com/docs/git-revert)

