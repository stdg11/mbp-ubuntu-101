#MacBook Pro 10,1 Ubuntu Installation/Configuration

## To Do

 - [ ] Keyboard brightness 0 on startup
 - [ ] Confirm Shutdown on power button
 - [ ] Apple keyboard bindings
 - [ ] Refind + Boot screen retina
 - [ ] Audio Mute
 - [ ] Auto install script
 - [ ] Make things pretty
 - [ ] zsh
 - [x] ~~Install Wireless drivers~~
 - [x] ~~Keyboard Backlight~~
 - [x] ~~Set keyboard layout on startup~~

## Install Broadcom Wireless Drivers

Once Ubuntu is installed you will have no network connections.
To install the wireless drivers located in drivers/:

 1. Install DKMS

    `dkpg -i dkms_2.2.0.3-1.1ubuntu5_all.deb`

 2. Install Wireless Drivers

    `dkpg -i bcmwl-kernel-source_6.30.223.141+bdcom-0ubuntu2_amd64.deb`

For the latest drivers see: http://packages.ubuntu.com/

## Confirm Shutdown on Power Button

## Keyboard Backlight

Credit to [Fran Diéguez](http://www.frandieguez.com/blog/2010/06/24/macbook-pro-keyboard-backlight-keys-on-ubuntu-gnulinux/)

 1. Copy`scripts/kb` to `/usr/bin`
 2. Don't forget to make it executable
 
    `sudo chmod +x /usr/bin/kb`

 3. Edit your sudoers file and append.

    `user ALL=NOPASSWD: /usr/bin/kb`

 4. Bind your function keys by editing `~/.i3/config`

    ```
    # keyboard brightness
    bindsym XF86KbdBrightnessDown exec "sudo kb down"
    bindsym XF86KbdBrightnessUp exec "sudo kb up"

    ```

 5. To turn your backlight off on startup, add the following to your `~/.i3/config`

    `exec_always sudo kb off `

## Set Keyboard Layout

 1. Add the following to your `~/.zshrc`

    `setxkbmap us -variant colemak`

 2. To switch you can either create an alias or i3 $mod key command

    ```
    # ~/.zshrc
    alias colemak="setxkbmap us -variant colemak"
    alias qwerty="setxkbmap gb"
    ```

## Wallpaper

 1. Install [FEH](http://feh.finalrewind.org/)
    
    `sudo apt-get install feh` 
 
 2. Edit your `~/.i3/config` and add the following to start feh on startup
    
    `exec --no-startup-id feh --bg-scale '/home/user/Pictures/wallpaper/cubes-2560x1600.jpg'`

## Lock Screen

 Credit to Pato [Lankenau](http://plankenau.com/blog/post/gaussian-blur-lock-screen-i3lock/)

 1. Install required packages

    `sudo apt-get install i3lock scrot imagemagick xautolock`

 2. Copy `scripts/lock` to `usr/bin/lock`

 3. Make it executable

    `sudo chmod +x /usr/bin/lock`

 4. To enable autolock add the following to `~/.i3/config`

    `exec_always xautolock -time 10 -locker lock`

## Installed Packages

 * i3lock
 * scrot
 * imagemagick
 * xautolock
 * zsh
 * i3
 * setxkbmap
 * [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)(eastwood theme)
 * curl
 * git
 * vim
 * flashplugin-installer
 * thunderbird
 * [dmenu2](https://bitbucket.org/melek/dmenu2)
 * libxft-dev
 * libx11-dev
 * feh
 * libxcb-randr0-dev
 * libxcb-xinerama0-dev
 * libxcb-xinerama0
