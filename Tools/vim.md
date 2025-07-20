# vim安装
apt安装的vim一般版本较低而且不支持支援Python3，所以采用源码编译的方式安装vim
此处支援的意思是指编译出来的Vim将内置对应语言的支持，允许在Vim脚本中使用对应语言编写复杂逻辑，一些Vim插件依赖某些语言
## 依赖环境
### 需要支援Python3
```
sudo apt install python3 python3-dev
```
### 需要支援lua和正则
```
sudo apt install lua5.3 liblua5.3-dev libperl-dev -y
```
### 需要支援Ruby
```
sudo apt install ruby-dev -y
```
## clone 源码
```
git clone https://github.com/vim/vim.git
```
## configure 配置
```
./configure \
--with-features=huge \
--enable-rubyinterp \
--enable-fail-if-missing \
--enable-luainterp \
--enable-perlinterp \
--enable-fontset \
--enable-python3interp \
--with-python3-command=python3
```
如果你修改你的vim安装地址你只需添加--perfix=“你的地址”

## 编译和安装
```
sudo make -j4
sudo make install
```
此处`-j4`是多线程编译，编译速度更快但是对核心要求更高，使用-j2或者不加也是可以的

### 如果安装时设定了非标准安装地址
```
echo 'export PATH="“你的地址”/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

# Vim配置
查看该文件同级目录下的vimrc，安装好vim-plug之后，执行命令:
```
cat vimrc >> ~/.vimrc
```
然后在vim打开~/.vimrc在命令模式下输入：
```
:PlugInstall
```
等待安装完即可
