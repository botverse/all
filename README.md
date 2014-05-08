# all

The tool for managing all the UI repos

## installation

```bash
$ git clone git@githubenterprise.pur3.net:fonz/all.git
$ mkdir -p ~/.local/bin
$ ln -s ~/REPO_LOCATION/all ~/.local/bin/all
$ echo "export PATH=$PATH:~/.local/bin" >> ~/.bash_profile
```

Place the file within your `$PATH`, I did it in `~/.local/bin` as I have it is already in my `$PATH`

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

and so on...ace the file within your $PATH, I did it in ~/.local/bin as I have it is already in my $PATH

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

