# collaboration workflow

Some terminology:

- repo = a location where a project's codebase is collected
- commit = a set of changes to the codebase. Signed, timestamped, and appended to a branch's version history.
- branch = a distinct version history of the codebase. You can switch between branches with `git checkout branch_name`
- local = a copy of the repo stored on your computer
- remote = a copy of the repo stored on a central host (e.g. GitHub). In our case, the remote is named `origin`.

The proposed workflow proceeds as follows. The authoritative version of the codebase exists in main. Do not commit to main directly. Instead, make commits to feature or development branches.  Merge changes from feature branches into main on the GitHub platform (i.e. a pull request).

## initial setup

Clone the project

```
git clone https://github.com/sboysel/copilot.git
```

List the active branch (and others available locally).

```
git branch -v
```

## collaboration workflow

Switch to main.

```
git checkout main
```

Pull latest changes. origin is the name of the remote, main is the name of the branch.

```
git pull origin main
```

Any time you want to make changes, **create a new branch first**.

```
git checkout -b feature/add-2sls-models
```

Make your changes...

After you've changed everything the way you want, review what has changed from git's perspective.

```
git status
```

Add the changes you want to commit back to the main repo.

```
git add path/to/file path/to/another/file
```

Commit the changes and add a message summarizing the changes.

```
git commit -m "informative commit message about the changes"
```

Push the commits to a new branch on remote.

```
git push -u origin feature/add-2sls-models
```

Open https://github.com/sboysel/copilot in a web browser and open a pull request. You will be merging the changes contained in the newly pushed branch into main.

Back on your local machine 

```
# delete the now merged development branch
git branch -d feature/add-2sls-models
# pull in the updated main branch
git checkout main
git pull origin main
```

and repeat the process from the top...
