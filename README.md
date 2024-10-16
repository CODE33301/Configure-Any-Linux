# Configure-Any-Linux
Configure Any Linux

## Configuration Steps
1. [Display Server](#20-Display-Server)
2. [Graphics Driver](#21-Graphics-Driver)
3. [Display Manager](#22-Display-Manager)
4. [Window Manager](#23-Window-Manager)
5. [Status Bars](#5-status-bars)


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
* i3bar
* i3block

### i3bar

### i3block
<b>Install i3blocks</b><br>
Arch Linux
```
pacman -S i3blocks
```

Configure i3block by file, you can save the file anyware and run the command.
```
status_command i3blocks -c ~/.config/ArchConfigs/OrangeTheme/i3blocks/i3blocks.conf
```

Default File Location
```
/etc/i3blocks.conf
```

Show Battery Life Dynamic
```
[battery]
command=cat /sys/class/power_supply/BAT0/capacity 
interval=10
```