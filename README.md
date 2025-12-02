
# 💤 LazyVim — Personal Starter Configuration

A fully customized **LazyVim** setup optimized for daily development on **Arch Linux**, including working Python/Node providers, Treesitter, Mason tools, and environment fixes.

> Đây là cấu hình NeoVim cá nhân của tôi — dùng để backup & restore dễ dàng trên mọi máy.  
> Repo này dựa trên LazyVim starter và đã được cấu hình thêm để tương thích với Arch Linux.


# Introduction

> A starter template for [LazyVim](https://github.com/LazyVim/LazyVim).
> Refer to the [documentation](https://lazyvim.github.io/installation) to get started.


## 🚀 Features

- ✔ Fully working **LazyVim 11+**
- ✔ Python provider (pynvim) via isolated venv `~/.nvim-python`
- ✔ Node provider using **NVM** (bypass Arch ICU issues)
- ✔ Mason + LSP automatic installation
- ✔ Treesitter + tree-sitter CLI installed
- ✔ Clean environment setup (no conflict with system Python)
- ✔ Optimized for long-term backup & system restore


## 📁 Folder Structure

~/.config/nvim
├── init.lua
├── lua/
│ ├── config/
│ ├── plugins/
│ └── ...
└── lazy-lock.json


## 🧩 Requirements

### 1️⃣ System Packages (Arch Linux)
```bash
sudo pacman -S git ripgrep fd fzf lazygit unzip wget tar gzip base-devel
```
###   Node.js Provider (NVM Recommended)
- Install Node.js and npm follow in this page [nodeJs](https://nodejs.org/en/download) to install nodejs and npm

###  # Install Neovim Node.js host

```bash
npm install -g neovim
```

#### ➕ Add NVM to Zsh (required)
- Thêm vào ~/.zshrc hoặc ~/.zprofile:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"   # Load nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```
⚠️ Khuyến nghị:

Đặt vào ~/.zprofile để đảm bảo nvm load cho mọi shell login.

----------------------------------------------------------------------------------
Không override PATH bằng cách ép /usr/bin:$PATH (sẽ phá NVM).
### 3️⃣ Python Provider (Using Isolated Virtual Environment)
- Không dùng Python system để tránh xung đột PEP 668.

```bash
python -m venv ~/.nvim-python
~/.nvim-python/bin/pip install pynvim
```

Thêm vào cấu hình NeoVim:

```bash
vim.g.python3_host_prog = "~/.nvim-python/bin/python"
```


