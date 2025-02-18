# Qtile
Download Qtile
sudo pacman -S qtile

# i3
Config Location
```
/etc/i3/config
```
Basic Bar
```
╭───────────────────────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                       │
│      i3bar Bottom | Start i3bar to display a workspace bar (plus the system information i3status      │
│                                                                                                       │
╰───────────────────────────────────────────────────────────────────────────────────────────────────────╯
bar {
    # i3bar_command i3bar --transparency
    # Can't fix wifi status with i3block
    status_command i3status -c ~/.config/archConfigs/purpleTheme/i3status/i3status.conf
    position top
    workspace_buttons yes
    #       <Top> <Right> <Bottom> <Left>
    padding 5px   5px     5px      0px
    colors {
    #   <colorclass>       <border> <background> <text>
        separator          #444444
    #   <i3 Bar>
        background         #000000
        statusline         #B1B1B1
    #   <i3 Bar Workstation Active>
        focused_workspace  #CECECE  #CECECE      #000000
        active_workspace   #333333  #333333      #888888
    #   <i3 Bar Workstation Border Color>
        inactive_workspace #333333  #333333      #f1f1f1
        urgent_workspace   #eb709b  #eb709b      #ffffff
    }
}
```
## Hyprland
### Installation
Install hyprland - The latest upstream release: `sudo pacman -S hyprland`
### Configuration
Configuration is done through a single configuration file
The default file is `/usr/share/hypr/hyprland.conf`
