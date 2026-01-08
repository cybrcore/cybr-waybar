```
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░░▒▓██████▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓███████▓▒░ ░▒▓██████▓▒░░▒▓███████▓▒░  
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓████████▓▒░░▒▓██████▓▒░░▒▓███████▓▒░░▒▓████████▓▒░▒▓███████▓▒░  
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░  ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░  ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
 ░▒▓█████████████▓▒░░▒▓█▓▒░░▒▓█▓▒░  ░▒▓█▓▒░   ░▒▓███████▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
```

# Result
<img src="../assets/inspiration/insp-waybar.png"/></td>
<p align="center">
  <em>waybar ↗ (top to bottom: secondary monitor, main monitor)</em>
</p>

> [!TIP]
> I included my own special tool for Waybar - if you hover over the red dot next between CPU temp and Notification center and scroll, you can adjust the brightness of your monitors (works on desktop via DDC/CI, OSD-free)

# Steps
### 0. Before you start
- Make sure [Geist Mono Nerd Font](../INSTALL.md##Prerequisites&Setup) is installed
- Make sure waybar is installed: `sudo pacman -S waybar`
- Make sure `git` is installed: `sudo pacman -S git`
- See [Installation Guide](../INSTALL.md) if you haven't set up prerequisites yet
- [Github](https://github.com/Alexays/Waybar) | [Arch Wiki](https://wiki.archlinux.org/title/Waybar)

### 1. Download waybar configs
```sh
#download waybar directory
git clone --depth=1 --filter=blob:none --no-checkout https://github.com/scherrer-txt/cybrland.git && cd cybrland && git sparse-checkout init --cone && git sparse-checkout set waybar && git checkout main && mv waybar ~/.config/ && cd ~ && rm -rf cybrland
```
↑ Unsure what this does? [Explanation](../INSTALL.md#How-sparse-checkout-works)  

### 2. Verify installation
```sh
ls -R ~/.config/waybar
```

You should see: `config.jsonc`, `modules.jsonc`, `style.css`, `scripts/`, `svg/`

<details>
<summary>Expected file structure</summary>

```
~/.config/waybar/
├── config.jsonc            # main settings
├── modules.jsonc           # module definitions
├── style.css               # visual styling
├── scripts/
│   ├── bright.sh           # brightness control (via mousescroll)
│   ├── bright-status.sh    # brightness values display
│   ├── cava.sh             # audio visualizer
│   └── mediaplayer.py      # media player info
└── svg/                    # graphical elements
    ├── gr0-left.svg
    ├── gr0-right.svg
    └── ...
```
</details>

### 3. Restart waybar
```sh
killall waybar && waybar
```