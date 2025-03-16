# Note to Self

> [!NOTE]
> Maybe I can be bothered to make into pages one day?


# Setting up Arch & Hyprland
> [!IMPORTANT]
> Don't be a dummy and copy the paths without amending the tokens! \
> `[user]` to be replaced with user name, e.g. "Snayff".

## Installations
1. Install endeavourOS.
	- Source https://endeavouros.com/
3. Run full update via terminal `pacman -Syu`.
4. Install JaKoolit Hyprland via terminal `sh <(curl -L https://raw.githubusercontent.com/JaKooLit/Arch-Hyprland/main/auto-install.sh)`.
	- Source: https://github.com/JaKooLit/Arch-Hyprland

# Configuring Hyprland
> [!IMPORTANT]
> Make a backup of any `.conf` file before making amends. (e.g. create a copy and rename with`.bak` at the end)

> [!NOTE]
> Example hyprland config: https://github.com/hyprwm/Hyprland/blob/main/example/hyprland.conf

## Current Issues
> [!CAUTION]
>  Cursor keeps resetting to default, rather than the defined bibata ones. 

## Define window rules:    
 1. Amend `WindowRules.conf` at `/home/[user]/.config/hypr/UserConfigs/`.
	- add opacity rules for firefox.
```
windowrulev2 = opacity 1.0 override, title: (.*YouTube.*)$
windowrulev2 = opacity 1.0 override, title: (.*Prime Video.*)$
windowrulev2 = opacity 1.0 override, title: (.*Netflix.*)$
windowrulev2 = opacity 1.0 override, title: (.*Twitch.*)$
windowrulev2 = opacity 1.0 override, title: (.*app.plex.*)$
windowrulev2 = opacity 1.0 override, title: (.*bbc*)$
```
> [!WARNING]
>  twitch, plex, bbc dont work. 🤷

## Define Screen Lock and Suspend Rules
> [!NOTE]
> All files found in this folder: `/home/[user]/.config/hypr/`.

1. Turn off idle and resume notifications.
   - comment out these lines in `hypridle.conf`, by placing a `#` at the start.
```
    #on-timeout = notify-send -i $iDIR " You are idle!"
    #on-resume = notify-send -i $iDIR " Oh! you're Back" " Hello !!!"
```
2. Turn on screen blanking on lock.
   - uncomment these lines in `hypridle.conf`:
```
listener {
    timeout = 630                            # 10.5 min
    on-timeout = hyprctl dispatch dpms off  # command to run when timeout has passed
    on-resume = hyprctl dispatch dpms on    # command to run when activity is detected after timeout has fired.
}
```


## Define SDDM/login screen:
1. Change theme:
	- Open theme file via terminal  `sudo nano /etc/sddm.conf.d/theme.conf.user`
    - Change listed theme. Ctrl-o + Enter to save, ctrl-x to exit.
```
[Theme]
Current=simple-sddm-2
```

## Change Waybar:
> [!NOTE]
> Review gallery here: https://github.com/JaKooLit/Hyprland-Dots/wiki/Gallery
> Gallery doesnt exactly match the options

### Choose Theme
> Themes I quite like: 
> 
> [Colored] Chroma Glow  ![image](https://github.com/user-attachments/assets/cf8b3faf-b391-4138-9847-0fa036f1cba1)
> 
> [Colourful] Oglo Chicklets   ![image](https://github.com/user-attachments/assets/80f0012e-886f-4686-9c59-ae32fb8f16c5)
> 
> [Colourful] Rainbow Spectrum (with amendments to the initial section) ![image](https://github.com/user-attachments/assets/58011de1-5a14-4470-992c-64aa4e80e83b)
> 
> [Catpuccin] Mocha ![image](https://github.com/user-attachments/assets/02eac06f-0403-497d-8d2b-7dcd66a772a5)
> 
> [Dark] Golden Eclipse  ![image](https://github.com/user-attachments/assets/48372cc8-84d5-4eb7-ad71-336cbf07508e)
> 
> [Dark] Half-moon ![image](https://github.com/user-attachments/assets/941617c3-8389-4e2b-88dc-ae3b5bf63460)
> 
> [Dark] Purpl ![image](https://github.com/user-attachments/assets/1bea4ea5-31fe-47a4-95a9-1a8f4da0669a)
> 
> [Extra] Modern Combined - Transparent ![image](https://github.com/user-attachments/assets/151cf1ef-c40b-460f-b2c0-0d201a600e17)
> 

1. SUPER + CTRL + B
2. choose desired style

### Choose Layout
> Layouts I quite like: 
>
> Default


2. SUPER + ALT + B
3. choose desired layout

  
## Define UserDecorations
1. Amend `UserDecorations.conf` at `/home/[user]/.config/hypr/UserConfigs/`.
	- change gap sizes
 		- increase gaps between windows `gaps_in = 4`
   		- increase gaps between windows and outer edge `gaps_out = 12`
  
## Mouse Settings
> [!NOTE]
> either add the inner line  to the existing `input` section or add the input section


1. Turn off mouse acceleration.
   - update `UserSettings.conf` with the following. 
```
input {
  accel_profile = flat
}
```

2. Turn off focus on mouse move.
   -  update `UserSettings.conf` with the following.
```
input {
  follow_mouse = false
}
```

3. Turn on paste with middle click.
   -  update `UserSettings.conf` with the following.
```
input {
  middle_click_paste = true
}
```

## Blue Light Filter with HyprSunset
> [!NOTE]
> Source: https://wiki.hyprland.org/Hypr-Ecosystem/hyprsunset/

1. `yay -S hyprsunset` in terminal.
2. In `Startup_Apps.conf` add the line
```
exec-once = hyprsunset
```
> [!CAUTION]
> might need to add a hyperctl call to set the temperature. https://wiki.hyprland.org/Hypr-Ecosystem/hyprsunset/#ipc


# Setting Up Apps
## Simple and Straightforward Installs
> [!NOTE]
> from Arch Package with `pacman -S [package name]` or AUR with `yay -S [package name]`
1. Steam
2. Firefox
3. Alacritty

## Spotify
> [!CAUTION]
> Not yet working

> [!NOTE]
> ! Plan !
> Install spotify then Spicetify: https://spicetify.app/docs/advanced-usage/installation/
> 
> ! Progress !
>
> No official app. Semi-official snap or ubuntu ver.
> 
> `sudo pacman -S spotify-launcher`
> gave this error:
>
> ```
> error: failed retrieving file 'libayatana-appindicator-0.5.93-1-x86_64.pkg.tar.zst' from ch.mirrors.cicku.me : The requested URL returned error: 404
> error: failed retrieving file 'libayatana-appindicator-0.5.93-1-x86_64.pkg.tar.zst' from mirror.osbeck.com : The requested URL returned error: 404
> error: failed retrieving file 'libayatana-appindicator-0.5.93-1-x86_64.pkg.tar.zst' from archlinux.cu.be : The requested URL returned error: 404
> error: failed retrieving file 'libayatana-appindicator-0.5.93-1-x86_64.pkg.tar.zst' from ftp.snt.utwente.nl : The requested URL returned error: 404
> ```




# TODO Lists
## Config Hyprland
Ref: https://wiki.hyprland.org/Configuring/Variables/

- Waybar config:
	- refer to these to determine amendments to make:
 		- https://github.com/JaKooLit/Hyprland-Dots/wiki/Customizing_waybar
		- https://github.com/Alexays/Waybar/wiki/Module:-Hyprland
		- https://wiki.hyprland.org/Useful-Utilities/Status-Bars/#waybar
	- use the bottom section from Layout:Summer Split: ![image](https://github.com/user-attachments/assets/a5329913-21e3-48c9-9430-3e871e7140da)
	- use the top right section from Layout:Everforest  ![image](https://github.com/user-attachments/assets/86c0868c-872c-4ce6-a24d-764e69afd7e2)
 	- Waybar fonts and font size:  https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#%EF%B8%8F-adjusting-fonts-sizes-and-font-scaling-including-waybar-fonts-and-kitty-terminal

- setup for nvidia:
	- https://wiki.hyprland.org/Nvidia/
- Can we clean up global hotkeys I won't use? https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#%EF%B8%8F-added-keybinds-but-does-not-work
- Configure workspace opening rules
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#-some-packages-are-opening-on-a-specific-workspaces
- - Animations
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#-hyprland-animations
- Config fast fetch
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_Terminal#fastfetch
- hard define border colours, prevent wallust overwriting
- create some default app groups:
	- dev:
 		- godot - main, left, no opacity
   		- gitkraken - bottom right
     	- browser - top right
	- work & watch:
 		-  browser, left and mid, no opacity
   		-  broswer, right, no opacity
- setup VSCode for editing Hyprland: https://marketplace.visualstudio.com/items?itemName=ewen-lbh.hyprland
- ? do we need to use nwg-look? https://github.com/nwg-piotr/nwg-look
- ? swap swappy for hyprshot or flameshot
- ? anything to copy from HyDE? https://github.com/Hyde-project/hyde
- ? swap to hyprpanel from waybar? https://github.com/Jas-SinghFSU/HyprPanel
- hyprland dotfile backups
- change dropdown terminal to use alacritty (and note about changing the default to alacritty)

## Functionality
- Swappy
	-  add to clipboard on capture
 	-  turn off sound on capture
