# Status Bars
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