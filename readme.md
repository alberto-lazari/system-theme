# ☀️ system-theme 🌙

A simple command that lets you switch between light and dark mode in macOS from the command-line and run custom commands on theme change

![system-theme demo](https://raw.github.com/alberto-lazari/system-theme/main/.github/demo.webp)

## Install

#### Homebrew

```bash
brew install alberto-lazari/formulae/system-theme
```

## Usage

Switch to light/dark mode with `system-theme light` or `system-theme dark`

Run `system-theme` with no arguments to get the current theme

Use `-h` or `--help` to learn more

### Run custom commands

You can run custom commands when switching to a different theme in the default `~/.config/system-theme/themerc` file. \
You can use the file to update the colorscheme of programs that don't support macOS appearance system natively

Here's an example to let Alacritty change colorscheme (some specific configuration is needed)

```shell
# Link your colorscheme file to current theme
# The $system_theme variable is either 'light' or 'dark'
# and is always available in `themerc`
ln -fs ~/.config/alacritty/colorscheme/$system_theme.toml \
  ~/.config/alacritty/colors.toml
# Trigger config reload
touch ~/.config/alacritty/alacritty.toml
```

You can change the default file location by exporting `$SYSTEM_THEME_RC` with
```bash
export SYSTEM_THEME_RC="/path/to/custom/rc"
```

# Credits

Inspired by [dark-mode](https://github.com/sindresorhus/dark-mode)
