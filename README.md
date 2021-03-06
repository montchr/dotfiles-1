# GoodGuyRy's dotfiles

Dev-related [packages](scripts/) and shell configuration. Very exciting.


## Download


#### Using Git

Clone the repository wherever convenient by ```cd```ing into the desired directory and running the following:

```shell
git clone https://github.com/goodguyry/dotfiles.git && cd dotfiles
```


#### Git-free

Download the files with the following:

```shell
curl -#L https://github.com/goodguyry/dotfiles/tarball/master | tar -xzv --exclude={README.md,LICENSE,PACKAGES.md}
```

Then ```cd``` into the downloaded directory.


## Install

```shell
./init
```


The following options are available when running the init file:

| Option                | Description                                    |
|-----------------------|------------------------------------------------|
| `-h`, `--help`        | Print this help text                           |
| `-c`, `--copy`        | Copy the files instead of symlinking           |
| `-n`, `--no-packages` | Suppress package installations and updates     |
| `-s`, `--server`      | Skip Projects folder and macOS-related packages |

**Notes:**
- `--copy` and `--server` also suppress initializing a Git repo and pulling updates from Github.
- `editorconfig` is always copied.


### Local configuration

**Filename:** `~/.dotfiles.local`

Used to add extraneous functionality (aliases, functions, prompts, etc.) without committing that information to the repo.


### macOS defaults

The setup process will prompt to apply the masOS defaults. They can also be applied independently from the dotfiles directory:

```
./scripts/macos
```

Take time to read through the [macos file](scripts/macos) to know what settings and applications will be impacted before executing the file.


## Acknowledgements

[Necolas Gallagher](http://github.com/necolas/dotfiles)

[Mathias Bynens](http://github.com/mathiasbynens/dotfiles)

[Mat Marquis](https://github.com/wilto/)

---

Copyright (C) Ryan Domingue

Offered as-is with no guarantee or warranty, offered nor implied.
