# Arch
## Configuration Steps
1. [Display Server](#1-display-server)
2. [Graphics Driver](#2-graphics-driver)
3. [Display Manager](#3-display-manager)
4. [Window Manager](#4-window-manager)
5. [Status Bars](#5-status-bars)
6. [Audio](#6-audio)
7. [Bluetooth](#7-bluetooth)
<!--#########################################################-->
# 1. Display Server
## Xorg
Install Xorg
```shell
sudo pacman -S xorg-server xorg-apps xorg-xinit
```
## Wayland
Install Wayland
```shell
sudo pacman -S wayland
```
You Can Check The Current Running Display Server: `echo $XDG_SESSION_TYPE`

<!--#########################################################-->
# 2. Graphics Driver
Install VGA Compatible Controller
```shell
sudo pacman -S xf86-video-ati
```
<!--#########################################################-->
# 3. Display Manager
## Pick Login Theme
Default Greeter
```shell
sudo pacman -S lightdm-gtk-greeter
```
Elementary OS
```shell
sudo pacman -S lightdm-pantheon-greeter
```
GTK Based Greeter, Linux Mint Theme
```shell
sudo pacman -S lightdm-slick-greeter
```
Webkit2 Theming
```shell
sudo pacman -S lightdm-webkit2-greeter
```
Modern Full Featured Webkit2
```shell
sudo pacman -S lightdm-webkit2-theme-litarvan
```
## Install Packages
```shell
pacman -S lightdm
```
## Edit Lightdm Configuration
List Available Greeters
```shell
ls -l /usr/share/xgreeters
```
Edit lightdm.conf
```shell
sudo nano /etc/lightdm/lightdm.config
```
Change Theme
```shell
[Seat:*]
...
greeter-session=lightdm-THEME-greeter
...
```
Enable lightdm
```shell
sudo systemctl enable lightdm
```
<!--#########################################################-->
# 4. Window Manager
## i3
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
<!--#########################################################-->
# 5. Status Bars
<b>Status Bars List</b>
* [i3status](#i3status)
* [i3block](#i3block)

<b>Cool Features</b>
* [Enable Transparency](#enable-transparency)

### Enable Transparency
```sh
bar {
    ...
    i3bar_command i3bar --transparency
    ...
}
```
### i3status
<b>Install i3blocks</b><br>
Arch Linux
```
pacman -S i3blocksi3status
```

Configure i3block by file, you can save the file anyware and run the command.
```sh
bar {
    ...
    status_command i3status -c ~/.config/ArchConfigs/OrangeTheme/i3status/i3status.conf
    ...
}
```

Default File Location
```sh
/etc/i3status.conf
```

Show date and time in, <b>Wednesday, October 16 2024 04:11 AM</b> format
```sh
tztime local {
        format = "%A, %B %d %Y %I:%M %p"
}
```
### i3block
<b>Install i3blocks</b><br>
Arch Linux
```
pacman -S i3blocks
```

Configure i3block by file, you can save the file anyware and run the command.
```sh
bar {
    ...
    status_command i3blocks -c ~/.config/ArchConfigs/OrangeTheme/i3blocks/i3blocks.conf
    ...
}
```

Default File Location
```sh
/etc/i3blocks.conf
```

Show Battery Life Dynamic
```sh
[battery]
command=cat /sys/class/power_supply/BAT0/capacity 
interval=10
```
<!--#########################################################-->
# 6. Audio
Works With XORG & Wayland
## Arch Linux
**Install pulseaudio-bluetooth**
```
sudo pacman -Syu pulseaudio-bluetooth
```
Kill all
```
sudo killall pulseaudio
```
Start pulseaudio
```
pulseaudio --start
```
Install pavucontrol & pavucontrol-qt
```
sudo pacman -Syu pavucontrol pavucontrol-qt
```
<!--#########################################################-->
# 7. Bluetooth
## Arch Linux
Install bluez-utils & blueman
```
sudo pacman -Syu bluez-utils blueman
```
Start Bluetooth
```
sudo systemctl start bluetooth
```
Start Bluetooth At Boot
```
sudo systemctl enable bluetooth
```
Open Bluetooth GUI
```
blueman-manager
```
Steps
* Pair MAC
* Trust MAC
* Connect MAC