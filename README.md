# Neovim Configuration

A personal Neovim configuration based on **NvChad v2**, managed with
`lazy.nvim` and tailored primarily for **Go** and **Lua** development.

## Features

- NvChad UI with the `tokyonight` theme, statusline, and buffer line
- Language Server Protocol support for Go (`gopls`) and Lua (`lua_ls`)
- Code completion and snippets with `nvim-cmp` and LuaSnip
- Automatic bracket and quote pairing with `nvim-autopairs`
- Treesitter highlighting and indentation for Go, Lua, and Vim
- Go formatting with `gofumpt`, `goimports-reviser`, and `golines`
- Go debugging with `nvim-dap` and `nvim-dap-go`
- File management with NvimTree
- File, text, and buffer search with Telescope
- Git integration with Gitsigns and `git-conflict.nvim`
- Integrated terminals, commenting, color highlighting, and indent guides

## Prerequisites

Install the following before using this configuration:

- [Neovim](https://neovim.io/) 0.11 or later
- [Git](https://git-scm.com/)
- [ripgrep](https://github.com/BurntSushi/ripgrep)
- [Go](https://go.dev/) for Go development features
- A [Nerd Font](https://www.nerdfonts.com/) for icons

## Installation

### 1. Install the required packages

On macOS, install the command-line dependencies with Homebrew:

```sh
brew install neovim git ripgrep go
```

If Homebrew is not installed, follow the instructions at
[brew.sh](https://brew.sh/).

### 2. Install a Nerd Font

This configuration uses Nerd Font icons. Install JetBrainsMono Nerd Font on
macOS:

```sh
brew install --cask font-jetbrains-mono-nerd-font
```

After installation, open your terminal settings and select
**JetBrainsMono Nerd Font** as the terminal font. Restart the terminal before
launching Neovim.

Other operating systems can download and install a font from the
[Nerd Fonts website](https://www.nerdfonts.com/font-downloads).

### 3. Back up the existing configuration

Skip this step if Neovim has not been configured before:

```sh
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
```

### 4. Clone this repository

```sh
git clone https://github.com/william1nguyen/nvim-config.git ~/.config/nvim
```

### 5. Start Neovim

```sh
nvim
```

On the first launch, the configuration automatically bootstraps `lazy.nvim`
and installs the required plugins. Wait for the installation to finish, then
restart Neovim.

## Post-installation

Install the configured language servers:

```vim
:MasonInstallAll
```

This installs `lua-language-server` and `gopls`.

Install the Go formatters used by `none-ls`:

```vim
:MasonInstall gofumpt goimports-reviser golines
```

Opening a Go file also loads `gopher.nvim`, which installs its additional Go
tools automatically.

Verify the installation with:

```vim
:checkhealth
:checkhealth vim.lsp
```

## Updating

Pull the latest configuration:

```sh
cd ~/.config/nvim
git pull
```

Update plugins, Mason packages, and Treesitter parsers from Neovim:

```vim
:Lazy sync
:MasonUpdate
:TSUpdate
```

Use `:NvChadUpdate` to update the NvChad components.
