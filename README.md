# Initial page

## Creat a repository and init git

```git
mkdir learngit
cd learngit
git flow init
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
- `git log [--pretty=online]` to check modification history

Remeber to use `q` to quit git log view.
If you quit with a abnormal command as `ctrt+C`, then your input will not show on the screen for ever.
To solve this, input `reset` to reload git bash.

## reset version

- `git reset HEAD^` return to the previous version
- `git reset --hard commit_id` to reset a specific commit version
- `git reflog` can check all the command you did at this local, so you can find the `futur` version id if you regret to return

- In case you have forgotten unstaged files, and you would like to recover them after `git rest`, use `git stash` before reset!
- In the worst case, you use `git rest --hard`, and did not commit or stash your unstaged files, then git cannot help you.
But you could search `local history` if you use VScode or some IDEs store the local history, if you saved that file before locally.
(thanks ctrl+S)
