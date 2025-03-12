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

## Configuration
> [!IMPORTANT]
> Make a backup of any `.conf` file before making amends.

> [!NOTE]
> Example hyprland config: https://github.com/hyprwm/Hyprland/blob/main/example/hyprland.conf

### Define window rules:    
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
>  twitch, plex, bbc dont work. 


### Define SDDM/login screen:
1. Change theme:
	- Open theme file via terminal  `sudo nano /etc/sddm.conf.d/theme.conf.user`
    - Change listed theme. Ctrl-o + Enter to save, ctrl-x to exit.
```
[Theme]
Current=simple-sddm-2
```

### Change Waybar:
> [!NOTE]
> Review gallery here: https://github.com/JaKooLit/Hyprland-Dots/wiki/Gallery
> Gallery doesnt exactly match the options

#### Choose Theme
> Themes I quite like: 
> 
> [Colored] Chroma Glow  ![image](https://github.com/user-attachments/assets/cf8b3faf-b391-4138-9847-0fa036f1cba1)
> [Colourful] Oglo Chicklets   ![image](https://github.com/user-attachments/assets/80f0012e-886f-4686-9c59-ae32fb8f16c5)
> [Colourful] Rainbow Spectrum (with amendments to the initial section) ![image](https://github.com/user-attachments/assets/58011de1-5a14-4470-992c-64aa4e80e83b)
> [Catpuccin] Mocha ![image](https://github.com/user-attachments/assets/02eac06f-0403-497d-8d2b-7dcd66a772a5)
> [Dark] Golden Eclipse  ![image](https://github.com/user-attachments/assets/48372cc8-84d5-4eb7-ad71-336cbf07508e)
> [Dark] Half-moon ![image](https://github.com/user-attachments/assets/941617c3-8389-4e2b-88dc-ae3b5bf63460)
> [Dark] Purpl ![image](https://github.com/user-attachments/assets/1bea4ea5-31fe-47a4-95a9-1a8f4da0669a)
> [Extra] Modern Combined - Transparent ![image](https://github.com/user-attachments/assets/151cf1ef-c40b-460f-b2c0-0d201a600e17)

1. SUPER + CTRL + B
2. choose desired style

#### Choose Layou

> Layouts I quite like (all shown with [Catpuccin] Mocha theme):
>
> Default ![image](https://github.com/user-attachments/assets/ac609172-7415-4b1e-ac88-37e5a40d7736)


2. SUPER + ALT + B
3. choose desired layout

#### Define UserSettings
1. Amend `UserSettings.conf` at `/home/[user]/.config/hypr/UserConfigs/`.
	- turn off auto focus on mouse move `follow_mouse = true`
 	- turn off mouse acceleration `  accel_profile = flat`
  	- turn on paste with middle mouse click `middle_click_paste = true`
  
#### Define UserDecorations
1. Amend `UserDecorations.conf` at `/home/[user]/.config/hypr/UserConfigs/`.
	- change gap sizes
 		- increase gaps between windows `gaps_in = 4`
   		- increase gaps between windows and outer edge `gaps_out = 12`

# TODO Lists
## Config Hyprland
- https://wiki.hyprland.org/Nvidia/
- Can we clean up global hotkeys I won't use? https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#%EF%B8%8F-added-keybinds-but-does-not-work
- Configure workspace opening rules
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#-some-packages-are-opening-on-a-specific-workspaces
- Waybar fonts and font size
 	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#%EF%B8%8F-adjusting-fonts-sizes-and-font-scaling-including-waybar-fonts-and-kitty-terminal
- Animations
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_KooL#-hyprland-animations
- Pick rofi and waybar themes
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/Gallery
- Config fast fetch
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/FAQ_Terminal#fastfetch
- Customise waybar
	- https://github.com/JaKooLit/Hyprland-Dots/wiki/Customizing_waybar
 	- use the bottom section from Layout:Summer Split: ![image](https://github.com/user-attachments/assets/a5329913-21e3-48c9-9430-3e871e7140da)
  	-  use the top right section from Layout:Everforest  ![image](https://github.com/user-attachments/assets/86c0868c-872c-4ce6-a24d-764e69afd7e2)

- hard define border colours, prevent wallust overwriting
- align windows to have a gap around the outside (away from edge) ![image](https://github.com/user-attachments/assets/57ccc2ba-6d5c-4364-af8b-87f4c1838f1d)
- tiling to cut horizontal
- create some default app groups:
	- dev:
 		- godot - main, left, no opacity
   		- gitkraken - bottom right
     	- browser - top right
	- work & watch:
 		-  browser, left and mid, no opacity
   		-  broswer, right, no opacity


## Functionality
- Swappy
	-  add to clipboard on capture
 	-  turn off sound on capture
