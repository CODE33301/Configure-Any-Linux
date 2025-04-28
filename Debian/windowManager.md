# Window Managers

1. The .xinitrc file
1. i3

## The .xinitrc file
create the `.xinitrc` file
```
touch .xinitrc
```

## i3
Install **i3** package
```
sudo apt install i3
```
### The .xinitrc file
Add `i3 -c ~/.config/i3/config` to `~/.xinitrc` file
### Config file
```
~/.config/i3/config
```
### Set the terminal
Find the commit `# start a terminal`
```
bindsym $mod+Return exec TERMINAL-NAME
```
Replace **TERMINAL-NAME** with the choice of temrinal
### Kill focused window
Find the commit `# kill focused window`
```
bindsym $mod+shift+q kill
```
I use `bindsym $mod+q kill` insted
### 