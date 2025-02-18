* Install awesomeWM
* Configuration

# Install AwesomeWM
Arch Linux: `sudo pacman -S awesome`<br>
Debian: `...`

# The main AwesomeWM "bar" module `awful.wibar`

# Configuration
The default `rc.lua` file is located in `/etc/xdg/awesome/rc.lua`. Add the default `rc.lua` file to `.config` folder `cp /etc/xdg/awesome/rc.lua ~/.config/awesome`
## Only show tags with clients or the current selected tag in the taglist
The `awful.widget.taglist` widget does support filtering which tag is listed.
```lua
s.mytaglist = awful.widget.taglist {
    screen = s,
    filter = function (t) return t.selected or #t:clients() > 0 end,
    buttons = taglist_buttons
}
```
## Set Main Terminal
`terminal = "TERMINAL-NAME"`
## Remove ![Icon](awesome64.png) launcher `awful.widget.launcher`
```lua
-- Remove
mylauncher = awful.widget.launcher({ image = beautiful.awesome_icon, menu = mymainmenu })
```
Remove **mylauncher**
```lua
-- Add widgets to the wibox
s.mywibox:setup {
  layout = wibox.layout.align.horizontal,
  { -- Left widgets
    layout = wibox.layout.fixed.horizontal,
    mylauncher,
    s.mytaglist,
    s.mypromptbox,
  },
  s.mytasklist, -- Middle widget
  { -- Right widgets
    layout = wibox.layout.fixed.horizontal,
    mykeyboardlayout,
    wibox.widget.systray(),
    batterywidget,
    mytextclock,
    s.mylayoutbox,
  },
}
```
## Battery Widget
```lua
batterywidget = wibox.widget.textbox()
batterywidget:set_text(" | Battery | ")
batterywidgettimer = timer({ timeout = 5 })
batterywidgettimer:connect_signal("timeout",
  function()
    fh = assert(io.popen("acpi | cut -d, -f 2,3 -", "r"))
    batterywidget:set_text(" |" .. fh:read("*l") .. " | ")
    fh:close()
  end
)
batterywidgettimer:start()
```
<!--###############################################################################################-->

<!--
## Installation
### Rofi
```
sudo pacman -Syu Rofi
```
## Configuration
### awful.wibar
#### Change Bar Location
```
s.mywibox = awful.wibar({position="top"})
s.mywibox = awful.wibar({position="bottom"})
```
#### Change Bar Height
```
s.mywibox = awful.wibar({height=25})
```
### Right Widget Battery
#### Install acpi
```
sudo apt install acpi
sudo pacman -S acpi
```
#### Add to rc.lua file - AwesomeWM 3.5 ^
```
batterywidget = wibox.widget.textbox()    
batterywidget:set_text(" | Battery | ")    
batterywidgettimer = timer({ timeout = 5 })    
batterywidgettimer:connect_signal("timeout",    
  function()    
    fh = assert(io.popen("acpi | cut -d, -f 2,3 -", "r"))    
    batterywidget:set_text(" |" .. fh:read("*l") .. " | ")    
    fh:close()    
  end    
)    
batterywidgettimer:start()
```
#### Add "batterywidget"
```
{ -- Right widgets
    ...
    batterywidget,
    ...
},
```
##### Output
Battery 1: discharging, 44%, 00:18:48 remaining
### Remove Tasklist Widget - Comment it to remove it
```
-- Create a tasklist widget
s.mytasklist = awful.widget.tasklist {
    screen  = s,
    filter  = awful.widget.tasklist.filter.currenttags,
    buttons = tasklist_buttons
}
```
### Restart AwesomeWM
```
Mod4 + Control + r
```
### Remove Title Bar
Change true to false
```
properties = { titlebars_enabled = false
```
### Remove floating windows - comment "awful.layout.suit.floating"
```
-- Table of layouts to cover with awful.layout.inc, order matters.
awful.layout.layouts = {
    ..
    --awful.layout.suit.floating,
    ..
}
-- }}}
```
### Network Manager Applet
#### Install Network Manager Applet Package
```
sudo pacman -S network-manager-applet
```
#### Autostart From The Confi File When At Boot
```
awful.spawn.with_shell("nm-applet")
```
### Blueman
#### Install Blueman
```
sudo pacman -Syu blueman
```
#### Enable Bluetooth
```
sudo systemctl enable bluetooth
```
## Picom
### Install
```
sudo pacman -Syu picom
sudo yay -S picom-git
```
### Start Custom Configuration File
```
picom --config /home/$USER/.config/picom/picom.conf
```
### By default it reads config ~/.config/picom.conf
### Kill Picom
```
pkill picom
```
## Keybinding
| Title  | Keybinding |
| ------------- | ------------- |
| ... | ... |

## Arc Icon Theme
For the [icons](https://github.com/horst3180/arc-icon-theme), then follow the installation instructions.

## Awesome WM Widgets
If you want any cool [widgets](https://github.com/streetturtle/awesome-wm-widgets) for your Awesome WM.

## ERRORs
### module 'awesome-wm-widgets.battery-widget.battery' not found
Follow the installation process [here](https://github.com/streetturtle/awesome-wm-widgets#installation)
### Battery Widget - Folder with icons doesn't exist: /usr/share/icons/Arc/status/symbolic
Follow the installation process [here](https://github.com/horst3180/arc-icon-theme#installation)
-->