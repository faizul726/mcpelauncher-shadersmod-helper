# mcpelauncher-shadersmod-helper
A helper script for mcpelauncher shadermod that symlinks materials based on top global pack for mcpelauncher-shadersmod `shaders` folder

![mcpelauncher-shadersmod-helper](https://github.com/user-attachments/assets/4ab3e6e6-3d89-4503-8fdc-4a6a7c4952c0)

## Requirements
* Have `jq` and [mcpelauncher-shadersmod](https://github.com/GameParrot/mcpelauncher-shadersmod) installed

## Limitations
* Only tested on Ubuntu 22.04 (apt installation)
* JQ can't process JSONC (json with comments)
* Can't find marketplace packs

## Features
* Symlinks `*.material.bin` files from top most activated global pack to `shaders` folder
* Subpacks are also supported
* Development packs are supported
* Empties shaders folder when top pack is not a shader

## Planned features
- [ ] Add flag/argument for launching mcpelauncher automatically
- [ ] Workaround for JQ jsonc issue
- [ ] Use [material-updater](https://github.com/mcbegamerxx954/material-updater) to update shaders
- [ ] Make an infinite loop that will keep scanning for resource pack changes and apply changes

## Usage

> [!IMPORTANT]  
> Make sure to change `$mcpelauncher_root` (line 4) and `$mcpelauncher_data` (line 8) according to your installations before using.  
>
> By default, those are set for apt installation in `$HOME/.local/share/mcpelauncher`

```
curl -L -O https://raw.githubusercontent.com/faizul726/mcpelauncher-shadersmod-helper/main/shadersmod-helper.sh
```

```
chmod +x shadersmod-helper.sh
```

```
./shadersmod-helper.sh
```

**Or one liner if you prefer...**

```
sudo apt install jq -y && curl -L -O https://raw.githubusercontent.com/faizul726/mcpelauncher-shadersmod-helper/main/shadersmod-helper.sh && chmod +x shadersmod-helper.sh && ./shadersmod-helper.sh
```

> [!TIP]  
> You can modify the script to automatically launch the game after symlinking is done.