---
title: "Setup new macOS"
date: 2023-03-12T15:43:42+08:00
draft: false
tags: [macOS, app, software, setup]
categories: [Setup]
---

## Install Apps
---------------

##### Via Mac Store
1. `wechat`
2. iWork
	- `Pages`
	- `Numbers`
	- `keynote`
3. `mindNode`
4. `YoudaoDict`
5. `QQ MUSIC`
6. `Slack`

##### Via Browser
1. `v2rayU`: https://github.com/yanue/V2rayU/releases
2. `brew`
	- https://docs.brew.sh/Installation
	- `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`
3. `Chrome`: https://www.google.com/chrome
4. `BaiduPan`: https://pan.baidu.com/download#pan
5. `Creative Cloud Installer`: https://account.adobe.com/?lang=en
6. `telegram`: https://desktop.telegram.org/
7. `qq doc`: https://docs.qq.com/desktop/
8. `filezilla`: https://filezilla-project.org/download.php?platform=osx
    - `host`: `sftp://example.com`, 
9. iTerm2: https://iterm2.com/downloads.html
10. `Vscode`: https://code.visualstudio.com/Download
11. `NetEase Music`: https://music.163.com/#/download
12. `ClashX Pro`: https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public

##### Via brew
1. `neovim`: 
    ```
    brew install --HEAD neovim
    ```
2. `youtube-dl`: 
    ```
    brew install youtube-dl
    ```

## Set up
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


