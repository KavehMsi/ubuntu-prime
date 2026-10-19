# ubuntu-prime

A declarative collection of system tweaks, dotfiles, and window manager configurations designed to transform a fresh Ubuntu installation into an optimized development environment.

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Zsh & Oh My Zsh](#zsh--oh-my-zsh)
  - [1. Install Zsh](#1-install-zsh)
  - [2. Set Zsh as Default Shell](#2-set-zsh-as-default-shell)
  - [3. Install Oh My Zsh](#3-install-oh-my-zsh)
- [Spaceship Prompt](#spaceship-prompt)
  - [1. Install Spaceship Theme](#1-install-spaceship-theme)
  - [2. Enable Spaceship in Zsh](#2-enable-spaceship-in-zsh)
  - [3. Font Requirements](#3-font-requirements)
- [Tmux Configuration](#tmux-configuration)
  - [1. Install Tmux](#1-install-tmux)
  - [2. Apply Configuration (`configs/.tmux.conf`)](#2-apply-configuration-configstmuxconf)
  - [3. Reload Configuration](#3-reload-configuration)

---

## Prerequisites

Ensure base tools like `curl` and `git` are installed:

```bash
sudo apt update && sudo apt install -y curl git
```

---

## Zsh & Oh My Zsh

[Zsh](https://www.zsh.org/) is an interactive shell with advanced autocompletion, path expansion, and theme support. [Oh My Zsh](https://ohmyz.sh/) is a framework for managing Zsh configurations, plugins, and themes.

### 1. Install Zsh

```bash
sudo apt update
sudo apt install -y zsh
```

Verify the installation:

```bash
zsh --version
```

### 2. Set Zsh as Default Shell

Change your default login shell to Zsh:

```bash
chsh -s $(which zsh)
```

> **Note:** Log out and log back in (or reboot) for the change to take full effect across your system.

### 3. Install Oh My Zsh

Install Oh My Zsh using the official installer script:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## Spaceship Prompt

[Spaceship](https://spaceship-prompt.sh/) is a minimalistic, powerful, and customizable prompt for Zsh that displays contextual information (Git branch/status, runtime versions, package versions, and more).

### 1. Install Spaceship Theme

Clone the Spaceship repository into Oh My Zsh's custom themes directory and create a symlink:

```bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship-prompt" --depth=1

ln -s "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship-prompt/spaceship.zsh-theme" "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship.zsh-theme"
```

### 2. Enable Spaceship in Zsh

Set `ZSH_THEME="spaceship"` in your `~/.zshrc` file:

```bash
sed -i 's/ZSH_THEME=".*"/ZSH_THEME="spaceship"/' ~/.zshrc
```

Then reload the configuration:

```bash
source ~/.zshrc
```

### 3. Font Requirements

Spaceship prompt requires Powerline glyphs and symbols. Install and configure a [Nerd Font](https://www.nerdfonts.com/) (e.g., *FiraCode Nerd Font*, *Meslo Nerd Font*, or *JetBrains Mono Nerd Font*) in your terminal emulator for symbols to render properly.

---

## Tmux Configuration

[tmux](https://github.com/tmux/tmux) is a terminal multiplexer that lets you manage multiple terminal sessions, windows, and panes within a single window.

This repository includes a custom configuration file at [`configs/.tmux.conf`](configs/.tmux.conf) which features:
- **Prefix key:** Remapped to `Ctrl+a` (instead of `Ctrl+b`)
- **Indexing:** Windows and panes start at 1 instead of 0
- **Pane Splitting:** Split with `|` (horizontal) and `-` (vertical) while preserving the current directory
- **Navigation:** Alt + Arrow keys to switch panes without pressing the prefix
- **Usability:** Mouse support enabled, Vi mode navigation, and custom status bar styling

### 1. Install Tmux

```bash
sudo apt update
sudo apt install -y tmux
```

### 2. Apply Configuration (`configs/.tmux.conf`)

Symlink the configuration file to your home directory so any updates in this repo are reflected automatically:

```bash
# Run from the root of this repository
ln -sf "$(pwd)/configs/.tmux.conf" ~/.tmux.conf
```

*(Alternatively, copy it directly if you prefer not to use a symlink: `cp configs/.tmux.conf ~/.tmux.conf`)*

### 3. Reload Configuration

If tmux is currently running, reload the configuration with:

```bash
tmux source-file ~/.tmux.conf
```

Or inside an active tmux session, press `Ctrl+a` followed by `r`.

- [Prerequisites](#prerequisites)
- [Zsh & Oh My Zsh](#zsh--oh-my-zsh)
  - [1. Install Zsh](#1-install-zsh)
  - [2. Set Zsh as Default Shell](#2-set-zsh-as-default-shell)
  - [3. Install Oh My Zsh](#3-install-oh-my-zsh)
- [Spaceship Prompt](#spaceship-prompt)
  - [1. Install Spaceship Theme](#1-install-spaceship-theme)
  - [2. Enable Spaceship in Zsh](#2-enable-spaceship-in-zsh)
  - [3. Font Requirements](#3-font-requirements)
- [Tmux Configuration](#tmux-configuration)
  - [1. Install Tmux](#1-install-tmux)
  - [2. Apply Configuration (`configs/.tmux.conf`)](#2-apply-configuration-configstmuxconf)
  - [3. Reload Configuration](#3-reload-configuration)

---

## Prerequisites

Ensure base tools like `curl` and `git` are installed:

```bash
sudo apt update && sudo apt install -y curl git
```

---

## Zsh & Oh My Zsh

[Zsh](https://www.zsh.org/) is an interactive shell with advanced autocompletion, path expansion, and theme support. [Oh My Zsh](https://ohmyz.sh/) is a framework for managing Zsh configurations, plugins, and themes.

### 1. Install Zsh

```bash
sudo apt update
sudo apt install -y zsh
```

Verify the installation:

```bash
zsh --version
```

### 2. Set Zsh as Default Shell

Change your default login shell to Zsh:

```bash
chsh -s $(which zsh)
```

> **Note:** Log out and log back in (or reboot) for the change to take full effect across your system.

### 3. Install Oh My Zsh

Install Oh My Zsh using the official installer script:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## Spaceship Prompt

[Spaceship](https://spaceship-prompt.sh/) is a minimalistic, powerful, and customizable prompt for Zsh that displays contextual information (Git branch/status, runtime versions, package versions, and more).

### 1. Install Spaceship Theme

Clone the Spaceship repository into Oh My Zsh's custom themes directory and create a symlink:

```bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship-prompt" --depth=1

ln -s "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship-prompt/spaceship.zsh-theme" "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/spaceship.zsh-theme"
```

### 2. Enable Spaceship in Zsh

Set `ZSH_THEME="spaceship"` in your `~/.zshrc` file:

```bash
sed -i 's/ZSH_THEME=".*"/ZSH_THEME="spaceship"/' ~/.zshrc
```

Then reload the configuration:

```bash
source ~/.zshrc
```

### 3. Font Requirements

Spaceship prompt requires Powerline glyphs and symbols. Install and configure a [Nerd Font](https://www.nerdfonts.com/) (e.g., *FiraCode Nerd Font*, *Meslo Nerd Font*, or *JetBrains Mono Nerd Font*) in your terminal emulator for symbols to render properly.

---

## Tmux Configuration

[tmux](https://github.com/tmux/tmux) is a terminal multiplexer that lets you manage multiple terminal sessions, windows, and panes within a single window.

This repository includes a custom configuration file at [`configs/.tmux.conf`](configs/.tmux.conf) which features:
- **Prefix key:** Remapped to `Ctrl+a` (instead of `Ctrl+b`)
- **Indexing:** Windows and panes start at 1 instead of 0
- **Pane Splitting:** Split with `|` (horizontal) and `-` (vertical) while preserving the current directory
- **Navigation:** Alt + Arrow keys to switch panes without pressing the prefix
- **Usability:** Mouse support enabled, Vi mode navigation, and custom status bar styling

### 1. Install Tmux

```bash
sudo apt update
sudo apt install -y tmux
```

### 2. Apply Configuration (`configs/.tmux.conf`)

Symlink the configuration file to your home directory so any updates in this repo are reflected automatically:

```bash
# Run from the root of this repository
ln -sf "$(pwd)/configs/.tmux.conf" ~/.tmux.conf
```

*(Alternatively, copy it directly if you prefer not to use a symlink: `cp configs/.tmux.conf ~/.tmux.conf`)*

### 3. Reload Configuration

If tmux is currently running, reload the configuration with:

```bash
tmux source-file ~/.tmux.conf
```

Or inside an active tmux session, press `Ctrl+a` followed by `r`.

