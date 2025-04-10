# Display Server
* [Wayland](#wayland)
* [XORG](#xorg)

## Wayland
Install Wayland
```shell
...
```

## XORG
Installing Xorg
```shell
$ sudo apt install xorg
```
without drivers and utilities
```shell
$ sudo apt install xserver-xorg-core
```

To have a proper graphic session starter, where `xxx` is to be replaced by the name of your video driver.
```shell
$ sudo apt install xserver-xorg-video-xxx xserver-xorg-core xinit
```
To find your video driver name
```
$ lspci -k | grep -EA3 'VGA|3D|Display'
```