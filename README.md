# GoodGuyRy's dotfiles

My dotfiles. Very exciting.

## Installation

#### Using Git

Clone the repository wherever convenient by ```cd```ing into the desired directory and running the following:

```bash
git clone https://github.com/goodguyry/dotfiles.git && cd dotfiles
```

#### Git-free

Download the files with the following:

```bash
curl -#L https://github.com/goodguyry/dotfiles/tarball/master | tar -xzv --exclude={README.md,LICENSE}
```

Then ```cd``` into the downloaded directory.

#### Setup Options

Run ```./init``` from inside the cloned or downloaded directory. The following options are available when running the init file:

<table>
    <tr>
        <td width="25%"><code>-h</code>, <code>--help</code></td>
        <td>Print this help text</td>
    </tr>
    <tr>
        <td width="25%"><code>--copy</code></td>
        <td>Copy the files instead of symlinking<br>"Copy mode" also suppresses initializing a Git repo and pulling updates from Github</td>
    </tr>
    <tr>
        <td width="25%"><code>--no-packages</code></td>
        <td>Suppress package installations and updates (including casks). These can be <a href="#package-managers">run independently</a> if need be.</td>
    </tr>
</table>

 Note: gitconfig and git_completion are always copied, regardless of the option passed.

#### Extras file

The '.extras' file prevents certain information from being committed to a public repository, and is also a great place to store functions and aliases that shouldn't be overwritten by future installations.

If the '.extras' file doesn't exist in the home directory, the script will prompt for Git author name and email, and an '.extras' file will be created in the home directory.

If the file exists, it will be presented for confirmation of the information it contains.

_Example .extras file:_

```bash
# Git credentials

# Add your name below
GIT_AUTHOR_NAME="Ryan Domingue"

# Add your email below
GIT_AUTHOR_EMAIL="ryan@aol.com"

GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"

# Set the credentials (modifies ~/.gitconfig)
git config --global user.name "$GIT_AUTHOR_NAME"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

## Package managers

- [Homebrew](http://brew.sh/)
- [Homebrew Cask](https://github.com/caskroom/homebrew-cask) (native applications)
- [Ruby Version Manager](https://rvm.io/)
- [Node Version Manager](https://github.com/creationix/nvm) and [Node Package Manager](https://www.npmjs.com/)

The [full list of installed software](http://github.com/goodguyry/dotfiles/blob/master/local/software_list.md) is available. In addition to package managers, some software is downloaded via ```wget``` to the 'Downloads' folder.

The package installation can be run at any time from the dotfiles directory:

All at once...


```bash
# All at once
source local/packages && run_packages
```

Or independently...

```bash
# Homebrew packages only
source local/packages && init_brew
```

```bash
# Homebrew casks
# Installs Homebrew if it's missing
source local/packages && init_casks
```

```bash
# Node Version Manager
source local/packages && init_nvm
```

```bash
# Node packages
# Installs Node if it's missing
source local/packages && init_npm
```

```bash
# Ruby Version Manager and gems
source local/packages && init_rvm
```

## OS X defaults

The setup process will prompt to apply the OS X defaults. They can also be applied independently from the dotfiles directory:

```
./bin/osx
```

Take time to read through the [osx file](http://github.com/goodguyry/dotfiles/blob/master/bin/osx) to know what settings and applications will be impacted before executing the file.

## Acknowledgements

[Necolas Gallagher](http://github.com/necolas/dotfiles)

[Mathias Bynens](http://github.com/mathiasbynens/dotfiles)

[Mat Marquis](https://github.com/wilto/)

---

Copyright (C) Ryan Domingue

Offered as-is with no guarantee or warranty, offered nor implied.
