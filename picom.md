# MyPicomConfig
## Installation
Arch
```
sudo yay -S picom-git
```
Fedora, RHEL9
```
sudo yum install dbus-devel gcc git libconfig-devel libdrm-devel libev-devel libX11-devel libX11-xcb libXext-devel libxcb-devel libGL-devel libEGL-devel libepoxy-devel meson pcre2-devel pixman-devel uthash-devel xcb-util-image-devel xcb-util-renderutil-devel xorg-x11-proto-devel xcb-util-devel
```

## To build
```
meson setup --buildtype=release build
ninja -C build
```

## To install
```
sudo ninja -C build install
```

## Errors
* **session_init FATAL ERROR ] Another composite manager is already running**
  ```
  ```

## Config
Create picom folder
```
mkdir ~/.config/picom
```
Download config file
```
wget https://raw.githubusercontent.com/CODE33301/Dotfiles/main/.config/picom/picom.conf?token=GHSAT0AAAAAACSTQVN2SLIPFHIFDRTAZVFSZSVIELQ
```
### Manually enable default compositing effects during a session.
```
picom &
```
### Run Picom
```
exec picom -b &
```
### Find a window’s class name.
* Run xprop and click on the target window.
  ```
  xprop
  ```
* Search the xprop output for the WM_CLASS(STRING) property, which will show the window class name.
  ```
  ...
  WM_CLASS(STRING) = "st-256color", "st-256color"
  ...
  ```
