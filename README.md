# Initial page

Mainly based on

- [(git tutorial)][https://www.liaoxuefeng.com/wiki/896043488029600] but modified.
- [(git flow tutorial)][https://git-flow.readthedocs.io/en/latest/presentation.html]

Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.

## Creat/clone and init git

If start with a local repository:

```git
mkdir learngit
cd learngit
git flow init
```

If start with a remote repository:

```git
git clone git@github.com:{github_username}/repository.git # by SSH (faster)
git clone https://github.com/{github_username}/repository.git  # by http
```

## Add commit

```git
git add README.md
git commit -m 'update the readme file'
```

After `-m` we can write down the commit message

## check the status

- `git status` to  get a review of the whole repository
- `git diff <filename>` to check the unstaged changes from the lastest version
- `git log [--pretty=online][--graph]` to check modification history

Remeber to use `q` to quit git log view.
If you quit with a abnormal command as `ctrt+C`, then your input will not show on the screen for ever.
To solve this, input `reset` to reload git bash.

## reset version

- `git reset HEAD^` return to the previous version
- `git reset commit_id` to reset a specific commit version
- `git reflog` can check all the command you did at this local, so you can find the `futur` version id if you regret to return

- In case you have forgotten unstaged files, and you would like to recover them after `git rest`, use `git stash` before reset!
- After stash, use `git stash pop` or `git stash apply` to resume your work. You can also use `git stash list` to review your stash.
- In the worst case, you use `git rest --hard`, and did not commit or stash your unstaged files, then git cannot help you.
But you could search `local history` if you use VScode or some IDEs store the local history, if you saved that file before locally.
(thanks ctrl+S)

## Branch checkout and merge

- `git branch` to check all the branches
- `git checkout branch_name` to switch to another branch, and discarg all the unstaged files
- `git merge dev` to merge `dev` into actual branch (so do switch branch before)

- `(develop) $ git pull --rebase` when other side changes have already been pushed to remote ahead of yours

## About remote

- `git remote -v` to check remote list and accessibility
- `git remote add {github_username} git@github.com:{github_username}/repository.git` to add a new remote by SSH
- `git push origin dev`, with your remote_name and remote_branch_name

## gitignore

- When you could not add a commit, `git check-ignore <filepath>` to check if a file is ignored by `.gitignore`

## config

- `git config --global alias.co checkout` to set `checkout` as `co` for usage

## git flow

- `git flow init` to start

- `git flow feature start my-great-feature` to creat a new branch `feature/my-great-feature` from `develop`
- `git flow feature rebase` to keep up-to-date if simple `git push` result in error  
- `git flow feature finish my-great-feature` to merge into `develop` and delect this branch
