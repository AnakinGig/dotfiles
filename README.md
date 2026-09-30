# Dotfiles

My personal configuration files, managed with [GNU Stow](https://www.gnu.org/software/stow/).

## Structure

The `dotfiles` directory mirrors your home directory.

Files and folders should be placed in the same structure as they appear in your home directory.

For example, if your home directory contains:

```text
/home/user/
├── .zshrc
└── .config/
    └── nvim/
        └── init.lua
```

Then your dotfiles repository should contain:

```text
/home/user/dotfiles/
├── .zshrc
└── .config/
    └── nvim/
        └── init.lua
```

In other words:

* Files directly in your home directory go directly in `dotfiles/`.
* Files inside `~/.config/` go inside `dotfiles/.config/`.
* Files inside any other directory should replicate the same directory structure inside `dotfiles/`.

This allows Stow to recreate the same structure in your home directory using symlinks.

## Installation

Clone the repository:

```bash
git clone git@github.com:AnakinGig/dotfiles.git ~/dotfiles
cd ~/dotfiles
```

Then run:

```bash
stow .
```

This will create symlinks for the files in `dotfiles/` inside your home directory.

## Removing the symlinks

From the `dotfiles` directory:

```bash
stow -D .
```

## Updating

Pull the latest changes:

```bash
cd ~/dotfiles
git pull
```

Then run:

```bash
stow .
```
