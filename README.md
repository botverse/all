Plce the file within your `$PATH`, I did it in `~/.local/bin` as I have it is already in my `$PATH`

**no arguments**

will apply `git pull upstream develop` to all repos

```bash
$ all
```

is equivalent to

```bash
$ all pull upstream develop
```

**any argument**

will be applied to the repos

```bash
$ all status
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

