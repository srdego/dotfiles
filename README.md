# Dotfiles

Welcome to my dotfiles! This repository is designed to work seamlessly with
[GNU Stow](https://www.gnu.org/software/stow/), allowing you to easily manage your dotfiles across multiple machines.

## Setup

For a single configuration directory run `stow -v -R -t ~ dir`.

- `v` Verbose.
- `R` Purge old links first.
- `t ~` Target home directory.
- `dir` Directory for symlinking.
