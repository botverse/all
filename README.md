# all

The tool for managing all the UI repos

## installation

```bash
$ git clone git@githubenterprise.pur3.net:fonz/all.git
```

Here a link is placed within `$PATH` scope, a local bin directory `~/.local/bin` is created and added to the `$PATH`

```bash
$ mkdir -p ~/.local/bin
$ ln -s ~/REPO_LOCATION/all ~/.local/bin/all
$ echo "export PATH=$PATH:~/.local/bin" >> ~/.bash_profile
```

## usage

**no arguments**

will apply `git status` to all repos

```bash
$ all
```

is equivalent to

```bash
$ all status
```

**any argument**

will be applied to the repos

```bash
$ all pull upstream develop
```

and so on...

**specify apps**

if you are working in a specific set of applications, you have to define the apps var

beign bundle represented as `./`

```bash
$ apps='./ app/common app/ui' all status
```

or define only once for that terminal session

```bash
$ export apps='app/common app/editor'
...
$ all status # will only do common and editor
```

**home folder**

if you define  `ALL_HOME` to point to your bundle directory, you can call `all`
from whichever directory:

```bash
$ echo export ALL_HOME=~/Projects/bundle >> ~/.bashrc
```

and then you can do `all status` from your editor directory, for example

## ~~pull requests~~

~~once you have create the branch and done all your commits you probably want to make a pull request to every repo

you need the [https://github.com/github/hub](github-cli) wrapper for this

also you need to configure the githubenterprise installation like this:

```bash
$ git config --global --add hub.host githubenterprise.pur3.net
```

then you are ready to go:

```bash
$ all pull-request -m "message of pull request" -b upstream:develop -h origin:MY_FEATURE
```
~~

