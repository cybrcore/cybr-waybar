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
<img src="../assets/inspiration/insp-waybar.png" width="800"/></td>

# Steps
### 0. Before you start
- Make sure [Geist Mono Nerd Font](../INSTALL.md##Prerequisites&Setup) is installed
- Make sure waybar is installed: `sudo pacman -S waybar`
- Make sure `git` is installed: `sudo pacman -S git`
- See [Installation Guide](../INSTALL.md) if you haven't set up prerequisites yet

### 1. Download waybar configs
```sh
#download waybar directory
git clone --filter=blob:none --no-checkout https://github.com/scherrer-txt/cybrland.git
cd cybrland
git sparse-checkout init --cone
git sparse-checkout set waybar
git checkout main

# move waybar directory to config directory
mv -i ~/cybrland/waybar ~/.config/

# delete cybrland directory
cd ~ && rm -rf cybrland
```
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