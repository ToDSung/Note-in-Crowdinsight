# wsl 開發環境

參考關鍵字 
我的 Windows Subsystem for Linux (WSL) 終極開發人員配置  

windows terminal

zsh

https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH

```shell=
sudo apt install zsh
zsh --version
```

oh my zsh

https://github.com/ohmyzsh/ohmyzsh

```shell=
# 有一個命令列 我選0
sh -c "$(curl -fsSL 
https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

```
plugins=(
    git
    git-open
    zsh-autosuggestions
    z
)

ZSH_THEME="agnoster"
"fontFace": "Cascadia Mono PL"
字體
https://github.com/microsoft/cascadia-code/releases
```

wsl 用 設定裡的應用程式裝
1. 安裝python 
    https://docs.microsoft.com/zh-tw/windows/python/web-frameworks
2. alias python=python3 pip=pip3 
3. 安裝 node 
    https://docs.microsoft.com/zh-tw/windows/nodejs/setup-on-wsl2
4. 安裝完 windows docker 後 
 https://nickjanetakis.com/blog/setting-up-docker-for-windows-and-wsl-to-work-flawlessly#ensure-volume-mounts-work
 
 wsl2