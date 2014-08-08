# all

Simple tool for managing several git repositories

## Installation

```bash
$ git clone git@github.com:botverse/all.git
```

Put all within the `$PATH` scope.

You can do this for example:

```bash
# create a local bin directory
$ mkdir -p ~/.local/bin
# symlink the all script
$ ln -s ~/REPO_LOCATION/all ~/.local/bin/all
# add the created bin directory to the path scope
$ echo "export PATH=$PATH:~/.local/bin" >> ~/.bash_profile
```

## Usage

By default `all` will understand that all the sub directories of the current `CWD` are git repositories, so having this directory structure.

```
 └ ~/workspace/
   ├ frontend/
   ├ backend/
   └ server/
```

you will be executing `all` in all the repos present in the current directory:

```bash
$ ~/workspace/$ all
```

you get:

```
frontend
On branch bootstrapping
nothing to commit, working directory clean

backend
On branch bootstrapping
nothing to commit, working directory clean

server
On branch bootstrapping
nothing to commit, working directory clean
```

You can tell `all` where the repositories are so you can execute it from *any* directory scope. Also you can specify which repositories to manage when working in a feature that won't affect all the repositories.

Check the configuration section for more information.

**calling `all` with no arguments**

will apply `git status` to all repos

```bash
$ all
```

is equivalent to

```bash
$ all status
```

**calling `all` with any argument**

will be applied to the repos

```bash
$ all pull upstream development
```

and so on...

## Configure

**Specify repos**

If you are working in a specific set of applications, you have to define the ALL_REPOS environment var:

```bash
$ ALL_REPOS='modules/http modules/rest' all status
```

or define only once for that terminal session:

```bash
$ export ALL_REPOS='modules/http modules/rest'
...
$ all status # will only check http and rest
```

**Home folder**

If you define  `ALL_HOME` to point to your workspace directory, you can call `all`
from whichever directory:

```bash
$ echo export ALL_HOME=~/workspace >> ~/.bashrc
```

and then you can do `all status` from the module directory you are currently working on.
