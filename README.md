gitbranch
=========

Gets the current branch and slaps it into your bash prompt.

Right now this depends on having an active virtualenv. That's kinda not the
best way to do things; if you're not working on a python git project it's
pretty useless unless you're willing to create meaningless virtualenvironments
for those non-python projects just to use this feature.

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

