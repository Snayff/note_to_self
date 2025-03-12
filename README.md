# Note to Self

> [!NOTE]
> Maybe I can be bothered to make into pages one day?

## Setting up Arch & Hyprland
> [!IMPORTANT]
> Don't be a dummy and copy the paths without amending the tokens! \
> `[user]` to be replaced with user name, e.g. "Snayff".

1. Install endeavourOS.
2. Setup window rules:
    - Amend `WindowRules.conf` at `/home/[user]/.config/hypr/UserConfigs/`.
       - add opacity rules for firefox.
```
windowrulev2 = opacity 1.0 override, title: (.*YouTube.*)$
windowrulev2 = opacity 1.0 override, title: (.*Prime Video.*)$
windowrulev2 = opacity 1.0 override, title: (.*Netflix.*)$
windowrulev2 = opacity 1.0 override, title: (.*Twitch.*)$
windowrulev2 = opacity 1.0 override, title: (.*app.plex.*)$
windowrulev2 = opacity 1.0 override, title: (.*bbc*)$
```
3. Configure SDDM/login screen:
   - Change theme:
     - Open theme file with `sudo nano /etc/sddm.conf.d/theme.conf.user`
     - Change listed theme. Ctrl-o + Enter to save, ctrl-x to exit.
```
[Theme]
Current=simple-sddm-2
```
4. 
