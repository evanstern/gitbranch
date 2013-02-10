gitbranch
=========

Gets the current branch and slaps it into your bash prompt.

Right now this depends on having an active virtualenv. That's kinda not the
best way to do things; if you're not working on a python git project it's
pretty useless unless you're willing to create meaningless virtualenvironments
for those non-python projects just to use this feature.

However, since you're explicitly mapping the relationship between a virtual
environment and the git project directory, I can tell you what branch you're
working on even if you're not actually in a git project directory any longer.

# Install

Copy `get_current_branch` somewhere on your PATH.

Copy `ps1.sh` somewhere on your PATH.

Copy (or append) `postactivate` into your .virtualenvs directory.

Copy (or append) `postdeactivate` into your .virtualenvs directory.

Copy `sample.env` into your .virtualenvs/<project> directory.

Rename `sample.env` to just `.env`

Update the new `.env` file so that `${PROJECT_DIRECTORY}` points to the actual
git project directory for this virtualenv project

Update your `~/.bashrc` so that the PS1 environment variable is the output of
the `ps1.sh` command. For example, you can add this to your ~/.bashrc file:

```
PS1=`ps1.sh`
```

# To use

Source your ~/.bashrc file

Issue a `workon` command to begin working on a specific virtualenv

If you've set everything up correctly, your command line should now have the
git current branch for that virtual environment.

NOTE: If you're not "working on" a virtual environment, you'll see [Inactive]
instead of a branch name.


# Plans

1. Get this to work without depending on an active virtualenv.

Possibly just degrade back to running a simple `get_current_branch` and if
you're in a project directory use that info.

2. Related to the above, either have some setting or change the default so that
   your branch info is gathered only if you're in the project directory.

Right now your branch info is gathered based on the virtualenv=>git-project
linkage you define. It may be that you don't want to do this but would rather
have the active branch info be dependant on what git project directory you are
currently inside of.


