# dotfiles

Configuration files managed with [GNU Stow](https://www.gnu.org/software/stow/).

## Prerequisites

- [GNU Stow](https://www.gnu.org/software/stow/) (`brew install stow` on macOS)
- [Neovim](https://neovim.io/) >= 0.9.0

## Setup

Clone this repo and run stow from inside it:

```bash
git clone <repo-url> ~/git/personal/dotfiles
cd ~/git/personal/dotfiles
stow -t ~ nvim
```

This creates a symlink at `~/.config/nvim` pointing into this repo.

## Packages

| Package | Target            | Description                          |
|---------|-------------------|--------------------------------------|
| `nvim`  | `~/.config/nvim`  | Neovim config (LazyVim-based)        |

## Adding a new package

Create a directory named after the package, mirroring the path relative to `$HOME`:

```
<package-name>/
└── .config/
    └── <app>/
        └── ...config files...
```

Then run:

```bash
stow -t ~ <package-name>
```

## Removing a package

```bash
stow -t ~ -D <package-name>
```
