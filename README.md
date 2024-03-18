# Git Cheat Sheet
Git is the open source distributed version control system that facilitates GitHub activities on your laptop or desktop. This cheat sheet summarizes commonly used Git command line instructions for quick reference.

## Install

### GitHub for Windows
https://windows.github.com

### GitHub for Mac
https://mac.github.com

### Git for All Platforms
http://git-scm.com

Git distributions for Linux and POSIX systems are available on the official Git SCM web site.

## Glossary
* **git:** An open source, distributed version-control system.

* **GitHub:** A platform for hosting and collaborating on Git repositories.

* **commit:** A Git object, a snapshot of your entire repository compressed into a SHA.

* **branch:** A lightweight movable pointer to a commit.

* **clone:** A local version of a repository, including all commits and branches.

* **remote:** A common repository on GitHub that all team member use to exchange their changes.

* **fork:** A copy of a repository on GitHub owned by a different user.

* **pull request:** A place to compare and discuss the differences introduced on a branch with reviews, comments, integrated tests, and more.

* **HEAD:** Representing your current working directory, the HEAD pointer can be moved to different branches, tags, or commits when using `git checkout`.

## Configure tooling
Configure user information for all local repositories.

* Sets the name you want attached to your commit transactions.
```sh
$ git config --global user.name "[name]"
```

* Sets the email you want attached to your commit transactions.
```sh
$ git config --global user.email "[email-address]"
```

* Enables helpful colorization of command line output.
```sh
$ git config --global color.ui auto
```

## Create repositories
When starting out with a new repository, you only need to do it once; either locally, then push to GitHub, or by cloning an existing repository.

* Turn an existing directory into a git repository.
```sh
$ git init
```

* Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.
```sh
$ git clone [url]
```

## The .gitignore file
Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named `.gitignore`. You can find helpful templates for `.gitignore`
files at https://github.com/github/gitignore.

## Synchronize changes
Synchronize your local repository with the remote repository on GitHub.com.

* Downloads all history from the remote tracking branches.
```sh
$ git fetch
```

* Combines remote tracking branch into current local branch.
```sh
$ git merge
```

* Uploads all local branch commits to GitHub.
```sh
$ git push
```

* Updates your current local working branch with all new commits from the corresponding remote branch on GitHub.
```sh
$ git pull
```

> [!NOTE]
> `git pull` is a combination of `git fetch` and `git merge`.

## Branches
Branches are an important part of working with Git. Any commits you make will be made on the branch you're currently “checked out” to. Use `git status` to see which branch that is.

* Creates a new branch.
```sh
$ git branch [branch-name]
```

* Switches to the specified branch and updates the working directory.
```sh
$ git checkout [branch-name]
```

* Combines the specified branch’s history into the current branch. This is usually done in pull requests, but is an important Git operation.
```sh
$ git merge [branch]
```

* Deletes the specified branch.
```sh
$ git branch -d [branch-name]
```

## Make changes
Browse and inspect the evolution of project files.

* Lists version history for the current branch.
```sh
$ git log
```

* Lists version history for a file, including renames.
```sh
$ git log --follow [file]
```

* Shows content differences between two branches.
```sh
$ git diff [first-branch]...[second-branch]
```

* Outputs metadata and content changes of the specified commit.
```sh
$ git show [commit]
```

* Snapshots the file in preparation for versioning.
```sh
$ git add [file]
```

* Records file snapshots permanently in version history.
```sh
$ git commit -m "[descriptive-message]"
```

## Redo commits
Erase mistakes and craft replacement history.

* Undoes all commits after [commit], preserving changes locally.
```sh
$ git reset [commit]
```

* Discards all history and changes back to the specified commit.
```sh
$ git reset --hard [commit]
```

> [!CAUTION]
> Changing history can have nasty side effects. If you need to change commits that exist on GitHub (the remote), proceed with caution. If you need help, reach out at github.community or contact support.
