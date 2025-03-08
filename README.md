# 🗃️ Dotfiles

Welcome to my dotfiles! This repository is designed to work seamlessly with
[GNU Stow](https://www.gnu.org/software/stow/), allowing you to easily manage
your dotfiles across multiple machines.

**📌 Table of Contents**

- [✨ Features](#-features)
- [📖 Usage](#-usage)
  - [🔗 Stowing](#-stowing)
  - [✂️ Unstowing](#-unstowing)

## ✨ Features

- **Modular setup**: Allows you to manage separate configurations for different
  software in individual directories.
- **No clutter**: Keeps your home directory clean by only creating symbolic links
  to configuration files, instead of copying files directly.

## 📖 Usage

To use it, follow these steps:

1. Clone this repository to a location of your choice (e.g., `~/projects/dotfiles`).
2. Navigate to the repository directory and run the `stow` command for any
   desired configuration folder.

For a single configuration directory, run:

```sh
stow -v -R -t ~ dir
```

Where:

- `-v`: Verbose mode, provides more output.
- `-R`: Recursively creates symlinks and purges old links if they exist.
- `-t ~`: Specifies the target directory where the symlinks should be created
  (typically your home directory `~`).
- `dir`: The directory that contains the configuration files you want to symlink.

### 🔗 Stowing

Let's say you want to stow the `git` configuration. Here's how to do it:

```bash
$ stow -v -R -t ~ git
LINK: .gitconfig => ~/projects/dotfiles/git/.gitconfig

$ ls -la ~
drwxr-xr-x 5 user user 4096 Jul  3 08:56 ~/projects/dotfiles
lrwxrwxrwx 1 user user   24 Jul  3 09:05 .gitconfig -> ~/projects/dotfiles/git/.gitconfig
```

In this example the `git` configuration located in `~/projects/dotfiles/git/.gitconfig`
is symlinked to the home directory as `.gitconfig`.

You can also stow multiple directories at once:

```sh
$ stow -v -R -t ~ bash git
```

### ✂️ Unstowing

To remove symlinks and undo the changes, you can use the `-D` flag:

```sh
stow -v -D -t ~ git
```

This will remove the symlink for `.gitconfig` and any other files linked from
the `git` directory.
