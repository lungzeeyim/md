---
title: "Setup My New macOS"
date: 2023-03-12T15:43:42+08:00
draft: false
tags: [macOS, app, software, setup]
categories: [Setup]
---

## Install Apps
---------------
##### Communication
- `wechat` (app store)
- `qq` (app store)
- `telegram`: https://desktop.telegram.org/
- `Slack`

##### Web tool
- `yt-dlp`: A youtube-dl fork with additional features and fixes
```
pip install yt-dlp
```
- `Chrome`: https://www.google.com/chrome
- `BaiduPan`: https://pan.baidu.com/download#pan
- `Filezilla`: https://filezilla-project.org/download.php?platform=osx
    - `host`: `sftp://example.com`, 
- `cctalke`: https://www.cctalk.com/download

##### Utilities
- `v2rayU`: https://github.com/yanue/V2rayU/releases
- `ClashX Pro`: https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public
- `brew`
    - https://docs.brew.sh/Installation
    - `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`


##### Entertainment
- `QQ MUSIC`
- `NetEase Music`: https://music.163.com/#/download

##### Productivity
- iWork
    - `Pages`
	- `Numbers`
	- `keynote`
- `mindNode`
- `YoudaoDict`
- `qq doc`: https://docs.qq.com/desktop/

##### Art
- `Creative Cloud Installer`: https://account.adobe.com/?lang=en

##### System tools:
- `rime-cantonese input method`: https://github.com/rime/rime-cantonese/releases


##### News
- `Reeder` (App store)

##### Dev tools:
- `JetBrains IDEs (IDEA, Webstorm, Pycharm)`: https://www.jetbrains.com/toolbox-app/
- `Insomnia`: https://insomnia.rest/download
- `node`
```
brew install node
```
- `yarn`
```
npm install --global yarn
```
- `gradle`
```
brew install gradle
```
- `wechat devtool`: https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html
- `neovim`: 
```
brew install --HEAD neovim
```
- iTerm2: https://iterm2.com/downloads.html
- `Vscode`: https://code.visualstudio.com/Download


## Setup
---------
##### Enable Chrome Download list layout:
chrome://flags/ -> enable `Enable download bubble`

##### brew/git issue
```
# sudo vim /etc/hosts, and add following:
199.232.28.133 raw.githubusercontent.com
```

##### Install Fonts
copy fonts to `/Users/zeeyim/Library/Fonts`

##### Terminal
Install Zsh: https://github.com/ohmyzsh/ohmyzsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Edit configuration of Zsh 
```
vim ~/.zshrc
```

##### Rime/Squirrel setting

Coustomize Squirrel menu 
```
sudo vim /Library/Input\ Methods/Squirrel.app/Contents/SharedSupport/default.yaml
```

Coustomize Squirrel menu 
```
vim /Users/zeeyim/Library/Rime/build/squirrel.yaml
vim /Users/zeeyim/Library/Rime/build/default.yaml
```

set default Chinese characters to simplified chinese (simplification/traditional):
`vim /Users/zeeyim/Library/Rime/build/jyut6ping3.custom.yaml`
```
patch:
    switches:
      - name: ascii_mode
        reset: 0
        states: ["中文", ABC]
      - name: full_shape
        states: ["半角", "全角"]
      - options: [noop, variants_hk, trad_tw, simplification]
        reset: 3
        states: ["傳統漢字", "香港傳統漢字", "臺灣傳統漢字", "大陆简化汉字"]
      - name: ascii_punct
        states: ["。，", "．，"]
      - name: emoji_suggestion
        states: ["冇 Emoji", "有 Emoji"]
```











