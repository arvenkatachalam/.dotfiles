# .dotfiles

macOS development environment configuration files, managed from `~/.config`.

## Tools

| Tool | Config | Purpose |
|------|--------|---------|
| [Neovim](https://neovim.io/) | `nvim/` | Editor (AstroNvim v5) |
| [Ghostty](https://ghostty.org/) | `ghostty/` | Primary terminal |
| [Alacritty](https://alacritty.org/) | `alacritty.toml` | Secondary terminal |
| [AeroSpace](https://github.com/nikitabobko/AeroSpace) | `aerospace/` | Tiling window manager |
| [Starship](https://starship.rs/) | `starship.toml` | Shell prompt |
| [Zellij](https://zellij.dev/) | `zellij/` | Terminal multiplexer |
| [Zsh](https://www.zsh.org/) | `zsh/` | Shell (syntax highlighting theme) |
| [btop](https://github.com/aristocratos/btop) | `btop/` | System monitor |
| [cava](https://github.com/karlstav/cava) | `cava/` | Audio visualizer |

A standalone [Kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim) config also lives at `init.lua` in the root.

## Theme

- **Colorscheme**: Tokyo Night (nvim, starship) / Catppuccin Mocha (terminals, zsh)
- **Font**: JetBrainsMono Nerd Font

## Setup

```sh
git clone git@github.com:arvenkatachalam/dotfiles.git ~/.config
brew bundle --file=~/.config/Brewfile
```

The `Brewfile` includes all Homebrew taps, formulae, casks, and VS Code extensions. To update it after installing/removing packages:

```sh
brew bundle dump --file=~/.config/Brewfile --force
```

Neovim plugins install automatically on first launch via lazy.nvim. Mason-managed tools (lua-language-server, stylua, debugpy) install on first open as well.
