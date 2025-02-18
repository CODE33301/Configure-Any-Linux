# Display Server
* [Wayland](#wayland)
* [XORG](#xorg)

## Wayland
Install Wayland
```shell
sudo pacman -S wayland
```
You Can Check The Current Running Display Server: `echo $XDG_SESSION_TYPE`

## XORG
Install Xorg
```shell
sudo pacman -S xorg-server xorg-apps xorg-xinit
```