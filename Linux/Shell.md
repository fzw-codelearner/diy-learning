<!-- vim-markdown-toc GFM -->

* [切换为zsh](#切换为zsh)
    * [安装zsh](#安装zsh)
    * [切换](#切换)
* [zsh配置](#zsh配置)
    * [oh my zsh 美化](#oh-my-zsh-美化)
    * [设置powerlevel10k为主题](#设置powerlevel10k为主题)
    * [插件配置](#插件配置)
        * [zsh-autosuggestions](#zsh-autosuggestions)
        * [zsh-syntax-highlighting](#zsh-syntax-highlighting)
        * [z](#z)
        * [以上插件还需添加至.zshrc中](#以上插件还需添加至zshrc中)

<!-- vim-markdown-toc -->
# 切换为zsh
## 安装zsh
```
sudo apt install zsh
```
## 切换
```
chsh -s /bin/zsh
```
重启后即可

# zsh配置
一开始进入zsh会有配置引导界面，可以选择创建空白.zshrc
## oh my zsh 美化
安装oh-my-zsh：
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
或者
```
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```
## 设置powerlevel10k为主题
安装
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
vim打开.zshrc修改如下：
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```
vim保存之后，执行
```
source ~/.zshrc
```

## 插件配置
### zsh-autosuggestions
zsh的自动补全插件，安装：
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
### zsh-syntax-highlighting
zsh的语法高亮插件，安装：
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
### z
zsh快速文件夹跳转插件
### 以上插件还需添加至.zshrc中
修改为：
```
plugins=(
     # other plugins...
     zsh-autosuggestions
     zsh-syntax-highlighting
     z
)
```

