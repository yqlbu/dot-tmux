# TMUX Configuration

<!-- vim-markdown-toc GFM -->

* [Install Powerline](#install-powerline)
* [Reload Configuration](#reload-configuration)
* [Plugins Manager](#plugins-manager)
    * [tmux-mem-cpu-load](#tmux-mem-cpu-load)
    * [Tmux Resurrent](#tmux-resurrent)
    * [Tmux Continuum](#tmux-continuum)
    * [Tmux Session Manager](#tmux-session-manager)

<!-- vim-markdown-toc -->

## Install Powerline

```bash
# archlinux
sudo pacman -S powerline
sudo pacman -S tmux

# ubuntu
sudo apt install powerline -y
sudo apt install tmux -y
```

## Reload Configuration

```bash
tmux source-file ~/.tmux.conf
```

## Plugins Manager

Install Tmux Plugin Manager

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Put this at the bottom of ~/.tmux.conf

```bash
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'github_username/plugin_name#branch'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

Reload TMUX environment so TPM is sourced:

```bash
# type this in terminal if tmux is already running
tmux source ~/.tmux.conf
```

Installing plugins

- Add new plugin to `~/.tmux.conf` with set `-g @plugin` '...'
- Press `prefix` + `I` (capital i, as in Install) to fetch the plugin.

Uninstalling plugins

- Remove (or comment out) plugin from the list.
- Press `prefix + alt + u` (lowercase u as in uninstall) to remove the plugin.

Key Bindings

`prefix + I`

- Installs new plugins from GitHub or any other git repository
- Refreshes TMUX environment

`prefix + U`

- updates plugin(s)

`prefix + alt + u`

- remove/uninstall plugins not on the plugin list

### tmux-mem-cpu-load

```bash
git clone https://github.com/thewtex/tmux-mem-cpu-load ~/.tmux/plugins/tmux-mem-cpu-load
cd ~/.tmux/plugins/tmux-mem-cpu-load
cmake .
make
sudo make install
```

### Tmux Resurrent

```bash
cd ~/.tmux
mkdir plugins
git clone https://github.com/tmux-plugins/tmux-resurrect.git ~/.tmux/plugins/tmux-resurrect
```

### Tmux Continuum

```bash
cd ~/.tmux
mkdir plugins
git clone https://github.com/tmux-plugins/tmux-continuum.git ~/.tmux/plugins/tmux-continuum
```

### Tmux Session Manager

Source: https://github.com/joshmedeski/t-smart-tmux-session-manager

```bash
set -g @plugin 'joshmedeski/t-smart-tmux-session-manager'
```
