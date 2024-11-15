# Configure-Any-Linux
Configure Any Linux

## Configuration Steps
1. [Display Server](#20-Display-Server)
2. [Graphics Driver](#21-Graphics-Driver)
3. [Display Manager](#22-Display-Manager)
4. [Window Manager](#23-Window-Manager)
5. [Status Bars](#5-status-bars)
6. [Audio](#6-audio)
7. [Bluetooth](#7-bluetooth)



# 1. Display Server
* Install Packages
```shell
sudo pacman -S xorg-server xorg-apps xorg-xinit
```



# 2. Graphics Driver
* Install VGA Compatible Controller
```shell
sudo pacman -S xf86-video-ati
```



# 3. Display Manager
## Pick Login Theme
* Default Greeter
```shell
sudo pacman -S lightdm-gtk-greeter
```
* Elementary OS
```shell
sudo pacman -S lightdm-pantheon-greeter
```
* GTK Based Greeter, Linux Mint Theme
```shell
sudo pacman -S lightdm-slick-greeter
```
* Webkit2 Theming
```shell
sudo pacman -S lightdm-webkit2-greeter
```
* Modern Full Featured Webkit2
```shell
sudo pacman -S lightdm-webkit2-theme-litarvan
```
## Install Packages
```shell
pacman -S lightdm
```
## Edit Lightdm Configuration
* List Available Greeters
```shell
ls -l /usr/share/xgreeters
```
* Edit lightdm.conf
```shell
sudo nano /etc/lightdm/lightdm.config
```
* Change Theme
```shell
[Seat:*]
...
greeter-session=lightdm-THEME-greeter
...
```
* Enable lightdm
```shell
sudo systemctl enable lightdm
```



# 4. Window Manager



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



# 6. Audio
**Install pulseaudio-bluetooth**
```
sudo pacman -Syu pulseaudio-bluetooth
```



# 7. Bluetooth