# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a macOS dotfiles/configuration directory (`~/.config`). It contains personal configurations for terminal tools, editors, window management, and shell customization.

## Two Neovim Configurations

There are two independent Neovim configs in this repo:

1. **`nvim/`** — AstroNvim v5+ based config using lazy.nvim. This is the primary active config.
   - Entry: `nvim/init.lua` bootstraps lazy.nvim, then loads `lua/lazy_setup.lua` and `lua/polish.lua`
   - `lua/lazy_setup.lua` loads AstroNvim core, community modules, and `lua/plugins/` directory
   - Plugin specs go in `lua/plugins/*.lua` as individual files returning LazySpec tables
   - Leader key: `<Space>`, local leader: `,`
   - Colorscheme: `tokyonight-night` (set in `lua/plugins/astroui.lua`)
   - LSP tools managed via Mason (`lua/plugins/mason.lua`): lua-language-server, stylua, debugpy, tree-sitter-cli
   - Claude Code integration via `lua/plugins/claudecode.lua` with `<leader>a` prefix keybinds
   - `lua/community.lua` and `lua/polish.lua` are currently disabled (early-return guards)

2. **`init.lua`** (root) — Kickstart.nvim based config (standalone, not used by the `nvim/` directory). This is an alternative/backup config using a single-file approach with inline lazy.nvim setup.

## Lua Formatting

StyLua is the Lua formatter. Config in `nvim/.stylua.toml`:
- 120 column width, 2-space indentation, Unix line endings
- `collapse_simple_statement = "Always"`, `call_parentheses = "None"`

## Terminal & Shell

- **Ghostty** (`ghostty/config`): Primary terminal. Catppuccin Mocha theme, JetBrainsMono Nerd Font Mono, 70% opacity with blur.
- **Alacritty** (`alacritty.toml`): Secondary terminal. Catppuccin Mocha theme, JetBrainsMono Nerd Font, 70% opacity.
- **Starship** (`starship.toml`): Shell prompt. Custom Tokyo Night-themed powerline segments with OS, directory, git, language versions, docker, and time modules.
- **Zsh** (`zsh/`): Contains `catppuccin-mocha.zsh` syntax highlighting theme.

## Window Management

- **AeroSpace** (`aerospace/aerospace.toml`): Tiling window manager. Alt+hjkl for focus, Alt+Shift+hjkl for move, Alt+1-9 for workspaces. Workspaces 1-5 on main monitor, 6-9 on secondary. Service mode via Alt+Shift+semicolon.

## Theme Consistency

Tokyo Night (terminals/nvim/starship) and Catppuccin Mocha (terminals/zsh) are used across tools. Font is JetBrainsMono Nerd Font everywhere.
