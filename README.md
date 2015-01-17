# mpb-ubuntu-101
MacBook Pro 10,1 Ubuntu Installation/Configuration

## To Do

 * Keyboard Brightness 0 on startup
 * ~~Colemak on startup~~
 * Confirm Shutdown on power button
 * ~~kEyboard Bindings~~
 * ReFiNd Boot screen retina
 * Audio Mute
 * auto script

# Install Broadcom Wireless Drivers

Once Ubuntu is installed you will have no network connections.
To install the wireless drivers located in drivers/:

 1. Install DKMS

    dkpg -i dkms_2.2.0.3-1.1ubuntu5_all.deb

 2. Install Wireless Drivers

    dkpg -i bcmwl-kernel-source_6.30.223.141+bdcom-0ubuntu2_amd64.deb

For the latest drivers see: [http://packages.ubuntu.com/]

# Confirm shutdown on Power Button

# Keyboard Backlight

Credit to [Fran Diéguez](http://www.frandieguez.com/blog/2010/06/24/macbook-pro-keyboard-backlight-keys-on-ubuntu-gnulinux/)

 * Copy `scripts/kb` to `/usr/bin`
 * Don't forget too `sudo chmod +x /usr/bin/kb`
 *

# Wallpaper

 * Install [FEH](http://feh.finalrewind.org/)
    sudo apt-get install feh 
 * Run feh on startup to set the Wallpaper
    vim ~/.i3/config
    exec --no-startup-id feh --bg-scale '/home/user/Pictures/wallpaper/cubes-2560x1600.jpg'
exec_always ~/.scripts/kb-off.sh 

# Installed Packages

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
