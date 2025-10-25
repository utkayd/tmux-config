# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a tmux configuration repository located at `~/.config/tmux/`. It contains a modular setup with a main configuration file and a separate statusline configuration.

## Configuration Structure

The configuration is split into two main files:

1. **tmux.conf** - Main tmux configuration file that:
   - Declares tmux plugins via TPM (Tmux Plugin Manager)
   - Configures Catppuccin theme with macchiato flavor
   - Enables mouse support
   - Initializes TPM

2. **statusline.conf** - Legacy custom statusline configuration (currently disabled in favor of Catppuccin theme)
   - Contains a Gruvbox-inspired custom theme
   - Can be re-enabled by uncommenting the source line in tmux.conf

## Plugin Management

This configuration uses **TPM (Tmux Plugin Manager)** located at `~/.tmux/plugins/tpm/`.

Active plugins:
- `tmux-plugins/tpm` - Plugin manager itself
- `tmux-plugins/tmux-sensible` - Sensible default settings
- `jaclu/tmux-menus` - Menu system for tmux
- `laktak/extrakto` - Text extraction tool
- `catppuccin/tmux` - Catppuccin theme (configured with macchiato flavor)

### Managing Plugins

After modifying plugin declarations in tmux.conf:
- Install new plugins: `prefix + I` (capital I)
- Update plugins: `prefix + U`
- Uninstall removed plugins: `prefix + alt + u`

Or via command line:
```bash
~/.tmux/plugins/tpm/bin/install_plugins
~/.tmux/plugins/tpm/bin/update_plugins all
~/.tmux/plugins/tpm/bin/clean_plugins
```

## Reloading Configuration

After editing configuration files, reload tmux:
```bash
tmux source ~/.config/tmux/tmux.conf
```

Or from within tmux: `prefix + :` then `source ~/.config/tmux/tmux.conf`

## Theme Configuration

Currently using **Catppuccin** theme with **macchiato** flavor.

To change the flavor, modify `@catppuccin_flavor` in tmux.conf:
- `latte` - Light theme
- `frappe` - Dark theme
- `macchiato` - Dark theme (current)
- `mocha` - Darkest theme

Additional Catppuccin customization options available at: https://github.com/catppuccin/tmux

### Legacy Custom Theme

The `statusline.conf` file contains a Gruvbox-inspired custom theme that is currently disabled. To use it instead of Catppuccin:
1. Comment out the Catppuccin plugin line in tmux.conf
2. Uncomment the `source ~/.config/tmux/statusline.conf` line
3. Reload tmux configuration
