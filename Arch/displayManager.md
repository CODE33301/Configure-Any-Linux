# Ly

# LightDM
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