![](1.jpg)

# Termux菜鸟教程

©knifefire著，转载请注明出处哦

## [如果你没有任何命令行经验，那么请先看我！！！](http://jason-hue.github.io/terminal/)

[点此加作者QQ](https://qm.qq.com/cgi-bin/qm/qr?k=JfLh15cfSzG0vziJz6EdW67XrIlSMpdM&noverify=0)

对于没有电脑，却又想成为一名天才极客的童鞋们简直就是不要太好

我是春节才开始接触termux的，之后就一发不可收拾。

## 初始化

第一次启动Termux的时候需要从远程服务器加载数据，然而可能会遇到这种问题：


    Ubable to install
    Termux was unable to install the bootstrap packages.
    Check your network connection and try again.

这里的Termux官方远程的服务器地址是: http://termux.net/bootstrap/

目前解决方法有两种：

VPN 全局代理 （成功率很高）

如果你是 WiFi 的话尝试切换到运营商流量 （有一定成功率）

① Google Play 

② F-Droid 

③ 酷安 根据这个顺序重复1、2操作

基本操作:

基本操作还是要学习一下的，可以事半功倍。

缩放文本

可以使用缩放手势来调整其字体大小。 对就是 双指放大缩小照片那样操作。

长按屏幕

长按屏幕会调出显示菜单项（包括复制、粘贴、更多），方便我们进行复制或者粘贴

菜单的说明如下：

长按屏幕
    
    ├── COPY:    # 复制
    ├── PASTE:   # 粘贴
    ├── More:    # 更多
    ├── Select URL:             # 提取屏幕所有网址
    └── Share transcipt:        # 分享命令脚本
    └── Reset:                  # 重置
    └── Kill process:           # 杀掉当前会话进程
    └── Style:                  # 风格配色 需要自行安装
    └── Keep screen on:         # 保持屏幕常亮
    └── Help:                   # 帮助文档

会话管理

显示隐藏式导航栏，可以新建、切换、重命名会话session和调用弹出输入法

同时在Android的通知栏中也可以看到当前Termux运行的会话数：

常用按键

常用键是PC端常用的按键如: ESC键、Tab键、CTR键、ALT键，有了这些按键后可以提高我们日常操作的效率，所以Termux后面的版本默认都是显示这个扩展功能按键的。

打开和隐藏这个扩展功能按键目前有下面两种方法：

方法一

从左向右滑动,显示隐藏式导航栏,长按左下角的KEYBOARD

方法二

使用Termux快捷键:音量++Q键 或者 音量++K键

当然这个常用按键在 Termux 后面的版本也支持自定义的，详情见本文的「进阶配置」-「定制常用按键」这一小节。

基础知识

这些基础知识简单了解一下就可以了，Linux 用的多了 就会慢慢熟悉理解了。

快捷键表

Ctrl键是终端用户常用的按键，但大多数触摸键盘都没有这个按键，因此 Termux 使用音量减小按钮来模拟Ctrl键。

例如，在触摸键盘上按音量减小+ L就相当于是键盘上按Ctrl + L的效果一样，达到清屏的效果。

    Ctrl + A -> 将光标移动到行首
    Ctrl + C -> 中止当前进程
    Ctrl + D -> 注销终端会话
    Ctrl + E -> 将光标移动到行尾
    Ctrl + K -> 从光标删除到行尾
    Ctrl + U -> 从光标删除到行首
    Ctrl + L -> 清除终端
    Ctrl + Z -> 挂起（发送SIGTSTP到）当前进程
    Ctrl + alt + C -> 打开新会话（仅适用于 黑客键盘）
音量加键也可以作为产生特定输入的特殊键.

    音量加 + E -> Esc键
    音量加 + T -> Tab键
    音量加 + 1 -> F1（音量增加 + 2 → F2…以此类推）
    音量加 + 0 -> F10
    音量加 + B -> Alt + B，使用readline时返回一个单词
    音量加 + F -> Alt + F，使用readline时转发一个单词
    音量加 + X -> Alt+X
    音量加 + W -> 向上箭头键
    音量加 + A -> 向左箭头键
    音量加 + S -> 向下箭头键
    音量加 + D -> 向右箭头键
    音量加 + L -> | （管道字符）
    音量加 + H -> 〜（波浪号字符）
    音量加 + U -> _ (下划线字符)
    音量加 + P -> 上一页
    音量加 + N -> 下一页
    音量加 + . -> Ctrl + \（SIGQUIT）
    音量加 + V -> 显示音量控制
    音量加 + Q -> 切换显示的功能键视
    音量加 + K -> 切换显示的功能键视图
快捷键用的熟悉的话也可以极大提高操作的效率。

基本命令

Termux 除了支持 apt 命令外，还在此基础上封装了pkg命令，pkg 命令向下兼容 apt 命令。apt命令大家应该都比较熟悉了，这里直接简单的介绍下pkg命令:


    pkg search <query>              # 搜索包
    pkg install <package>           # 安装包
    pkg uninstall <package>         # 卸载包
    pkg reinstall <package>         # 重新安装包
    pkg update                      # 更新源
    pkg upgrade                     # 升级软件包
    pkg list-all                    # 列出可供安装的所有包
    pkg list-installed              # 列出已经安装的包
    pkg show <package>              # 显示某个包的详细信息
    pkg files <package>             # 显示某个包的相关文件夹路径
建议大家使用 pkg 命令，因为 pkg 命令每次安装的时候自动执行 apt update 命令，很是方便

软件安装

除了通过上述的 pkg 命令安装软件以外，如果我们有 .deb 软件包文件，也可以使用 dpkg 进行安装。

    dpkg -i ./package.de         # 安装 deb 包
    dpkg --remove [package name] # 卸载软件包
    dpkg -l                      # 查看已安装的包
    man dpkg                     # 查看详细文档
目录结构

    echo $HOME
    /data/data/com.termux/files/home

    echo $PREFIX
    /data/data/com.termux/files/usr

    echo $TMPPREFIX
    /data/data/com.termux/files/usr/tmp/zsh
长期使用 Linux 的朋友可能会发现，这个HOME路径看上去和我们电脑端的不太一样，这是为了方便 Termux 提供的特殊的环境变量。

## 端口查看
Android 10 以下版本
Andorid 10 以下的版本是可以正常使用netstat 命令的，这样可以方便的查看端口开放信息
## 查看所有端口
netstat -an

## 查看3306端口的开放情况
netstat -an|grep 3306

Andorid 10 版本的Termux 下无法正常使用 netstat -an 命令，我的解决方法是安装一个 nmap，然后扫描本地端口（弯道超车）：

## 安装nmap端口扫描神器
pkg install nmap

## 扫描本地端口
nmap 127.0.0.1
使用 nmap 操作 纯属无奈之举，但是又不是不能用（源于：罗永浩名言 :-)）
进阶配置
要想使用体验好，进阶配置少不了。
## 更换国内源
使用pkg update 更新一下的时候发现默认的官方源网速有点慢，在这个喧嚣浮躁的时代，我们难以静下心等待，这个时候就得更换成国内的Termux清华大学源了，加快软件包下载速度。

### 方法一：自动替换（推荐）
可以使用如下命令自动替换官方源为 TUNA 镜像源
pkg update 卡住的话多按几次回车 不要傻乎乎的等


    sed -i 's@^\(deb.*stable main\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/termux-packages-24 stable main@' $PREFIX/etc/apt/sources.list

    sed -i 's@^\(deb.*games stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/game-packages-24 games stable@' $PREFIX/etc/apt/sources.list.d/game.list

    sed -i 's@^\(deb.*science stable\)$@#\1\ndeb https://mirrors.tuna.tsinghua.edu.cn/termux/science-packages-24 science stable@' $PREFIX/etc/apt/sources.list.d/science.list

    pkg update
更换源几秒钟就可以执行完pkg update了，心里顿时乐开了花。

### 方法二：手动修改

请使用内置或安装在 Termux 里的文本编辑器，例如 vi / vim / nano 等直接编辑源文件，不要使用 RE 管理器等其他具有 ROOT 权限的外部 APP 来修改 Termux 的文件

编辑 $PREFIX/etc/apt/sources.list 修改为如下内容
    
     The termux repository mirror from TUNA:
    deb https://mirrors.tuna.tsinghua.edu.cn/termux/termux-packages-24 stable main

编辑 $PREFIX/etc/apt/sources.list.d/science.list 修改为如下内容

    The termux repository mirror from TUNA:
    deb https://mirrors.tuna.tsinghua.edu.cn/termux/science-packages-24 science stable

编辑 $PREFIX/etc/apt/sources.list.d/game.list 修改为如下内容

    The termux repository mirror from TUNA:
    deb https://mirrors.tuna.tsinghua.edu.cn/termux/game-packages-24 games stable
安装基础工具

更换源之后来赶紧来下载安装一些基本工具吧，这些工具基本上是 Linux 系统自带的，因为 Termux 为了体积不过大，默认是没有带这些工具的，执行下面的命令来安装:
    pkg update
    pkg install vim curl wget git tree -y

## 终端配色方案

脚本项目地址：https://github.com/Cabbagec/termux-ohmyzsh/

该脚本主要使用了zsh来替代bash作为默认 shell，并且支持色彩和字体样式，同时也激活了外置存储，可以直接访问SD卡下的目录。主题默认为 agnoster，颜色样式默认为 Tango，字体默认为 Ubuntu。

执行下面这个命令确保已经安装好了 curl 命令

    sh -c "$(curl -fsSL https://github.com/Cabbagec/termux-ohmyzsh/raw/master/install.sh)"  
如果因为不可抗力的原因，出现port 443: Connection refused网络超时的情况，那么执行下面国光迁移到国内的地址的命令即可：

    sh -c "$(curl -fsSL https://html.sqlsec.com/termux-install.sh)"  
Android6.0 以上会弹框确认是否授权访问文件,点击始终允许授权后 Termux 可以方便的访问SD卡文件。


### 手机 App 默认只能访问自己的数据，如果要访问手机的存储，需要请求权限，如果你刚刚不小心点了拒绝的话，那么可以执行以下命令来重新获取访问权限:

    termux-setup-storage

脚本允许后先后有如下两个选项:

#### Enter a number, leave blank to not to change: 14
#### Enter a number, leave blank to not to change: 6
分别选择色彩样式和字体样式，重启Termux app后生效配置。不满意刚刚的效果，想要继续更改配色方案的话，可以根据下面命令来更改对应的色彩配色方案：

设置色彩样式：

输入chcolor命令更换色彩样式，或者：输入
    ~/.termux/colors.sh

设置字体

运行chfont更换字体，或者：
    ~/.termux/fonts.sh

创建目录软连接

执行过上面的一键配置脚本后，并且授予 Termux 文件访问权限的话，会在家目录生成storage目录，并且生成若干目录，软连接都指向外置存储卡的相应目录:

创建QQ文件夹软连接

手机上一般经常使用手机QQ来接收文件,这里为了方便文件传输,直接在storage目录下创建软链接.
QQ

    ln -s /data/data/com.termux/files/home/storage/shared/tencent/QQfile_recv QQ
TIM

    ln -s /data/data/com.termux/files/home/storage/shared/tencent/TIMfile_recv TIM

这样可以直接在home目录下去访问QQ文件夹，大大提升了工作效率。

## 定制常用按键

在 Termux v0.66 的版本之后我们可以通过 
    ~/.termux/termux.properties 

文件来定制我们的常用功能按键，默认是不存在这个文件的，我们得自己配置创建一下这个文件。

下面做尝试简单配置一下这个文件:

### 新建并编辑配置文件
    vim ~/.termux/termux.properties
内容为：

    extra-keys = [ \
 ['ESC','|','/','HOME','UP','END','PGUP','DEL'], \
 ['TAB','CTRL','ALT','LEFT','DOWN','RIGHT','PGDN','BKSP'] \
]

如果无法创建这个文件，那么得首先新建一下这个目录:
    mkdir ~/.termux

修改完成保存文件后，重启 Termux app生效配置：


可以直接输入特殊的字符串，例如上面的例子中的|就是一个字符串，此外 Termux 还有封装了一些特殊按键，入上面例子中的ESC就是 Termux 自带的按键，完整的特殊按键表如下：

    按键	说明
    CTR 特殊按键
    ALT	特殊按键
    FN	特殊按键
    ESC	退出键
    TAB	表格键
    HOME 原位键
    END	结尾键
    PGUP 上翻页键
    PGDN 下翻页键
    INS	插入键
    DEL	删除键
    BKSP 退格键
    UP	方向键 上
    LEFT 方向键 左
    RIGHT 方向键 右
    DOWN 方向键 下
    ENTER 回车键
    BACKSLASH 反斜杠 \
    QUOTE 双引号键
    APOSTROPHE 单引号键
    F1~F12 F1-F12按键

上面列出的三个特殊键中的每一个最多只能在附加键定义中列出一次，超过次数将会报错。

下面是我自用的按键表：

     extra-keys = [ \
 ['ESC','|','/','`','UP','QUOTE','APOSTROPHE'], \
 ['TAB','CTRL','~','LEFT','DOWN','RIGHT','ENTER'] \
]


## zsh 主题配色

编辑家目录下的.zshrc配置文件

   $ vim .zshrc

第一行可以看到,默认的主题是agnoster主题:


实际上这个主题也蛮酷的，如果你还想更换其他主题的话，那么在.oh-my-zsh/themes目录下放着oh-my-zsh所有的主题配置文件，只要将默认的 agnoster 更换为其他的主题文件名即可。
下面是我认为还不错的几款主题

agnoster
ys
robbyrussell

主题比较多，这里就不列举了，感兴趣大家可以一个个尝试去看看。 
当然如果你是个变态的话，可以尝试random 主题,每打开一个会话配色主题都是随机的.

    ZSH_THEME="random"

### zsh 插件推荐

zsh 之所以受欢迎除了好看的配色以为，另一个原因就是强大的插件了。下面列举一款比较实用的插件的安装方法，更多强大的插件等待大家自己去探索。

#### autosuggestions

根据用户的平时使用习惯，终端会自动提示接下来可能要输入的命令，这个实际使用效率还是比较高的：

#### 拷贝到 plugins 目录下
   
    git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

在 ~/.zshrc 中配置：

    Ini
    plugins=(其他的插件 zsh-autosuggestions)

输入zsh命令生效配置:

命令就自动提示补全了,在 Termux 里面的快捷键是 音量加 + D，就可以直接补全命令了。

## 修改启动问候语

这个默认启动问候语在前期对于初学者有一定的帮助，但是随着你们 Termux 的熟悉，这个默认的问候语就会显得比较臃肿。编辑问候语文件可以直接修改启动显示的问候语:

    vim $PREFIX/etc/motd

这样启动新的会话的时候看上去就会简洁很多。什么你也想要这个效果？ 呐 下面是我自己生成的，可以直接复制粘贴:
你可以直接复制这个：
     
         _____                                 
        |_   _|__ _ __ _ __ ___  _   ___  __
           | |/ _ \ '__| '_ ` _ \| | | \ \/ /
           | |  __/ |  | | | | | | |_| |>  < 
           |_|\___|_|  |_| |_| |_|\__,_/_/\_\

## 超级管理员身份

实际上 Termux 不需要 root 权限也可以折腾各种各样的操作的，大家不必对 root 抱有啥幻想，本文的操作基本上没有涉及到手机要用到 root 的地步。

### 手机没有root

利用proot可以为手机没有root的用户来模拟一个root的环境，这里主要是经典的 Linux 文件系统布局上的模拟。

    pkg install proot -y

然后终端下面输入:

    termux-chroot

即可模拟root环境，该环境模仿 Termux 中的常规Linux文件系统，但是不是真正的 root。
输入exit可回到普通用户的文件系统。

### 手机已经root

安装tsu，这是一个su的 Termux 版本，是一个真正的root权限，用来在termux上替代su，操作不慎可能对手机有安全风险。因为官方封装了，所以安装也很简单：

    pkg install tsu -y

然后终端下面输入:

    tsu

即可切换root用户，这个时候会弹出root授权提示，给予其root权限，效果图如下:

在管理员身份下，输入exit可回到普通用户身份。不过本文没有设计到 root 权限的操作，一些底层的工具可能才会需要，考虑到 root 的不安全性 和 那些工具的冷门性，国光这里就没有继续拓展。

## 开发环境

Termux 支持的开发环境很强，可以完美的运行 C、Python、Java、PHP、Ruby等开发环境，建议读者朋友们选择自己需要的开发环境折腾。

编辑器

写代码前总得折腾一下编辑器，毕竟磨刀不误砍柴工嘛。Termux 支持多种编辑器，完全可以满足日常使用需求。

### Emacs

据说Emacs是神的编辑器，可我这种小菜鸡还不会使用哎，但是 Termux 官方已经封装好了 Emacs了，我们安装起来就会简单很多:

     pkg install emacs  

### nano

nano 是一个小而美的编辑器。具有如下：打开多个文件，每行滚动，撤消/重做，语法着色，行编号等功能

同样安装起来也很简单：

    pkg install nano

### Vim

Vim 被称为编辑器之神，基本上 Linux 发行版都会自带 Vim，这个在前文基本工具已经安装了，如果你没有安装的话，可以使用如下命令安装：

    pkg install vim

并且官方也已经封装了vim-python，对Python相关的优化。

    pkg install vim-python

### 解决汉字乱码

如果你的Vim打开汉字出现乱码的话，那么在家目录(~)下,新建.vimrc文件

    vim .vimrc

添加内容如下:

    set fileencodings=utf-8,gb2312,gb18030,gbk,ucs-bom,cp936,latin1
    set enc=utf8
    set fencs=utf8,gbk,gb2312,gb18030

然后source下变量:

    source .vimrc


### Vim 配色

Termux Vim 自带了如下的配色：

    ls /data/data/com.termux/files/usr/share/vim/vim82/colors

    desert.vim   
    morning.vim    
    shine.vim    
    blue.vim      
    elflord.vim   
    murphy.vim     
    slate.vim    
    darkblue.vim 
    evening.vim   
    pablo.vim      
    industry.vim  
    peachpuff.vim  
    torte.vim    
    delek.vim     
    koehler.vim   
    ron.vim        
    zellner.vim

配色可以自己一个个尝试一下，还是向上面的汉字乱码那样，编辑家目录下的.vimrc文件：

    vim ~/.vimrc

新增如下内容：

    set nu                " 显示行号
    colorscheme desert    " 颜色主题
    syntax on             " 打开语法高亮

下面是我随便找的几个颜色主题效果，感兴趣的朋友可以自己一个个尝试：

=== slate ===

=== murphy===

=== peachpuff ===

## Apache

Apache是一个开源网页服务器软件，由于其跨平台和安全性，被广泛使用，是最流行的Web服务器软件之一。

安装 Apache

    pkg install apache2

启动 Apache

    apachectl start

然后浏览器访问: http://127.0.0.1:8080 访问是否成功启动：


Termux 自带的 Apache 的网站默认路径为：

    $PREFIX/share/apache2/default-site/htdocs/index.html

停止 Apache

    apachectl stop

重启 Apache

    apachectl restart

## Apache 解析 PHP

既然Apache、PHP、MySQL都成功安装的话，那么现在只要配置好 Apache 解析 PHP 之后就可以打造一个 Android 平台上的 LAMPP平台了。

## 安装 php-apache

默认的 Apache 是无法解析 PHP的，我们需要安装相应的包：

    pkg install php-apache

### 配置 Apache

Termux 上的 Apache 默认配置文件的路径为:

    $PREFIX/etc/apache2/httpd.conf

直接编辑配置文件:

    vim /data/data/com.termux/files/usr/etc/apache2/httpd.conf

配置文件里面搜索 PHP 没有相关的模块，所以需要我们手动添加 PHP7 的模块:

    LoadModule php7_module /data/data/com.termux/files/usr/libexec/apache2/libphp7.so 

并在刚刚这个语句下方添加解析器，内容如下:

    <FilesMatch \.php$>
      SetHandler application/x-httpd-php
    </FilesMatch> 

接着继续往下找配置文件里面配置默认首页的地方，我们添加 index.php 到默认首页的规则里面:

    <IfModule dir_module>
      DirectoryIndex index.php index.html
    </IfModule>

这表示网站目录的默认首页是 index.php，如果没有 index.php 系统会自动寻找 index.html做为默认首页了。

修改完 Apache 的配置文件后，记得使用 apachectl restart 重启 Apache 服务，然后这个时候回发现我们重启居然报错了：

    Apache is running a threaded MPM, but your PHP Module is not compiled to be threadsafe.  You need to recompile PHP.
    AH00013: Pre-configuration failed
不要慌问题不大，下面来解决这个问题

解决 Apache PHP 报错

先找到如下行

    LoadModule mpm_worker_module libexec/apache2/mod_mpm_worker.so

给他注释掉为:

    #LoadModule mpm_worker_module libexec/apache2/mod_mpm_worker.so

然后找到如下行:

    #LoadModule mpm_prefork_module libexec/apache2/mod_mpm_prefork.so

取消注释为:

    LoadModule mpm_prefork_module libexec/apache2/mod_mpm_prefork.so

就OK了



## 解析 PHP 测试

在 Apache 的网站根目录下，创建一个 index.php ，测试一下 phpinfo() 函数能否正常运行:

    echo '<?php phpinfo(); ?>' > $PREFIX/share/apache2/default-site/htdocs/index.php

然后浏览访问: http://127.0.0.1:8080 查看效果

## C

Termux 官方封装了 Clang，他是一个C、C++、Objective-C和Objective-C++编程语言的编译器前端。

### 安装 clang

    pkg install clang

编译测试

clang 在编译这一块很强大，感兴趣的朋友可以去网上查看详细的教程，这里只演示基本的 Hello World使用。写一个Hello World的C程序，如下 hello.c:

    #include <stdio.h>
    int main(){
      printf("Hello World")
      return 0;
    }

编辑完成后，使用 clang 来编译生成 hello 的可执行文件：

    clang hello.c -o hello

## Java

Termux 原生编译JAVA只能使用 ecj (Eclipse Compiler for Java) 和 dx 了，然后使用 Android 自带的 dalvikvm 运行。如果想要完整体验JAVA环境的话，另一个方法就是 Termux 里面安装一个完整的 Linux 系统，然后在 Linux里面运行Java，安装系统部分下面文章会详细介绍，这一节国光只介绍最基本的操作。

安装编译工具

    pkg install ecj dx -y

这里只演示基本的 Hello World 使用。写一个Hello World的 JAVA 程序，如下 HelloWorld.java:

    public class HelloWorld {
        public static void main(String[] args){
            System.out.println("Hello Termux");
        }
    }

编译生成 class 文件

    ecj HelloWorld.java

编译生成 dex 文件

    dx --dex --output=hello.dex HelloWorld.class

使用 dalvikvm 运行

格式规范如下：
    dalvikvm -cp dex文件名 类名

    dalvikvm -cp hello.dex HelloWorld

## MariaDB(MySQL)

MariaDB 是 MySQL 关系数据库管理系统的一个复刻，由社区开发，有商业支持，旨在继续保持在GNU GPL下开源。开发这个分支的原因之一是：甲骨文公司收购了 MySQL 后，有将 MySQL 闭源的潜在风险，因此社区采用分支的方式来避开这个风险。

安装 MariaDB

Termux 官方也封装了MariaDB，所以安全起来很方便：

    pkg install mariadb

这里基本上会安装很顺利，但是早期用户可能出现安装失败的情况，如果安装失败的话，这个时候手动在配置目录下创建my.cnf.d文件夹即可：

    $ cd /data/data/com.termux/files/usr/etc/
    $ mkdir my.cnf.d

初始化数据库

早期的 Termux 安装完 MySQL是需要初始化数据库的，新版本在安装时候就已经初始化了数据库

    mysql_install_db

2020年4月19日：今天安装的MySQL 发现已经存在 mysql.user 表了，无需初始化：


启动 MySQL 服务

因为正常启动完成后，MySQL这个会话就一直存活，类似与debug调试一样，此时使用Ctrl + C -> 中止当前进程也无济于事，体验式就一点都不优雅，所以这里使用Linux自带的nohup命令将其放到后台启动。

    nohup mysqld &

图片上这个17115此时就是mysqld的进程PID号，我们使用如下命令验证一下是否正确：

    ps aux|grep mysql

可以看到果然是进程的PID号

至于 nohup 运行的提示

    nohup: ignoring input and appending output to `nohup.out'

这个是正常现象，无伤大雅，Termux 下就这样将就着用吧。

停止 MySQL 服务

Termux 下没有好的办法退出 MySQL 服务，只能强制杀掉进程了，使用如下命令格式可以轻松杀掉进程：

    kill -9 PID

成功kill掉
当然每次查看进程的PID号，再杀掉进程有点繁琐了，实际上这一步可以直接这样操作：

    kill -9 `pgrep mysql`

Awesome ! 优雅!

## 默认的两个用户

用户登录的前提是MySQL服务在后台运行，如果你按照上一小节操作把MySQL kill掉的话，请重新启动一下MySQL服务

新版本的 Termux 安装初始化数据库的时候包含两个高权限用户，一个是无法访问的 root 用户

提示拒绝root登录

另一个用户就是 Termux 的用户名，默认密码为空，我们来登录看看：

    mysql -u $(whoami)

可以成功登录 并执行SQL语句
那么这个无法登录的 root 用户该怎么办呢 ？不要着急 继续往下看

修改 root 密码

老版本的 Termux 的直接使用mysql_secure_installation可以设置密码，但是新版本的安全策略变更了 我们在设置密码的时候回提示当前密码不正确，所以这条路行不通了。

这里我们只能使用MySQL的另一个用户名，即 Termux 用户名登录，然后来修改 root 的密码，使用如下命令修改 root 密码:

    # 登录 Termux 用户
    mysql -u $(whoami)

    # 修改 root 密码的 SQL语句
     use mysql;
    set password for 'root'@'localhost' = password('你设置的密码');

    # 刷新权限 并退出
    flush privileges;
    quit; 

OK！那么修改 root 密码就成功了。

## root 用户登录

修改完密码之后我们就可以美滋滋地使用 root 用户来登录了：

    mysql -u root -p
    Enter password: xxxxx（这里输入你的密码)

### 远程登录 MySQL

使用 ip a 后查看 IP 地址后，尝试电脑端远程访问 Termux 的数据库:


发现默认是无法成功连接的，这个时候我们需要到数据库手动开启 root 用户的远程访问权限:

这里的 P@ssw0rd 是我的 root 密码

    grant all on *.* to root@'%' identified by 'P@ssw0rd' with grant option;
    flush privileges;

执行完成后 尝试PC端远程过去看看:


## Nginx

Nginx 是一个高性能的 Web 和反向代理服务器，Nginx 用的熟悉的话，下面搭建各种网站也就轻而易举了。

### 安装 Nginx

Termux 安装 Nginx 也很简单，一条命令即可：

    pkg install nginx

安装完成后，我的习惯是查看一下版本信息：

#### 1.17.10 版本

### 测试 Nginx

测试检查 Nginx 的配置文件是否正常:

    nginx -t


现在测试肯定是OK的，这个多用于我们修改完 Nginx 的配置文件后的检查。

### 启动 Nginx

早期版本的 Termux 需要在termux-chroot 环境下才可以成功启动 Nginx ，新版本的 Termux 可以直接启动，很是方便：

    nginx

Termux 在 Nginx 上默认运行的端口号是 8080， 使用pgrep命令也可以查看 Nginx 进程相关的PID号。

然后手机本地直接访问http://127.0.0.1:8080 查看 Nginx 是否正常启动：


### 重启 Nginx

一般当修改完 Nginx 相关的配置文件时，我们需要重启 Nginx，使用如下命令即可重启:

    nginx -s reload

### 停止 Nginx

方法一 原生停止

    nginx -s stop

或者

    nginx -s quit

quit 是一个优雅的关闭方式，Nginx在退出前完成已经接受的连接请求。Stop 是快速关闭，不管有没有正在处理的请求。

方法二 杀掉进程

只需三番钟，里造会干我一样，爱象节款游戏  扯远了，只需要1条命令，即可优雅的终止掉 Nginx 服务:

    kill -9 `pgrep nginx`

貌似手机党 并不好敲 这个 ` 符号 =，= ，如果实在敲不出来，那就分两步走吧：

### 查询 nginx 进程相关的 PID 号
    
    pgrep nginx

### 杀掉 查询出的 PID号进程
    
    kill -9 PID

### Nginx 解析 PHP

Termux 下的 Nginx 解析 PHP 这里单独拿出一级标题来叙述，成功解析的话,下面安装 wordpress等 PHP网站就会轻松很多。

安装 php-fpm

Nginx 本身不能处理 PHP，它只是个 Web 服务器，当接收到 PHP 请求后发给 PHP 解释器处理。Nginx 一般是把请求转发给 fastcgi 管理进程处理，PHP-FPM 是一个PHP FastCGI管理器，所以这里得先安装它：

    pkg install php-fpm

安装完成顺便检查一下版本信息吧


### 配置 php-fpm

编辑 php-fpm 的配置文件 www.conf:

    vim $PREFIX/etc/php-fpm.d/www.conf

定位搜索 listen = 找到

    listen = /data/data/com.termux/files/usr/var/run/php-fpm.sock

将其改为：

    listen = 127.0.0.1:9000

？？？啥 你不会使用 vim 搜索 ㄟ(▔,▔)ㄏ 那就老老实实一个个翻页吧。

### 配置 Nginx

编辑 Nginx 的配置文件 nginx.conf:

    vim $PREFIX/etc/nginx/nginx.conf

下面是我贴出配置好的完整配置文件，大家可以参考下面这些图，只需要2大步骤：

    添加 index.php 到默认首页的规则里面

    取消 location ~ \.php$ 这些注释，按照图片上的 提示修改：

    Termux 里面的 Nginx 默认网站的根目为：

    /data/data/com.termux/files/usr/share/nginx/html
    如果想要修改默认路径的话 只需要在配置文件中 替换2处出现的这个路径即可

下面贴一份完整的配置文件：

    Nginx

    worker_processes  1;
    events {
        worker_connections  1024;
    }

    http {
        include       mime.types;
        default_type  application/octet-stream;
        sendfile        on;
        keepalive_timeout  65;

        server {
            listen       8080;
            server_name  localhost;
            location / {
                root   /data/data/com.termux/files/usr/share/nginx/html;
                index  index.html index.htm index.php;
            }

            error_page   500 502 503 504  /50x.html;
            location = /50x.html {
                root   /data/data/com.termux/files/usr/share/nginx/html;
            }

            location ~ \.php$ {
                root           html;
                fastcgi_pass   127.0.0.1:9000;
                fastcgi_index  index.php;
                fastcgi_param  SCRIPT_FILENAME  /data/data/com.termux/files/usr/share/nginx/html$fastcgi_script_name;
                include        fastcgi_params;
            }
        }
    }
### 测试 PHP 解析

Nginx 默认网站的根目录为：

    /data/data/com.termux/files/usr/share/nginx/html

在这个网站根目录下新建 info.php 内容为：
    <?php phpinfo(); ?>

    echo '<?php phpinfo(); ?>' > $PREFIX/share/nginx/html/info.php

### 启动服务

先启动 php-fpm 服务：

    php-fpm

然后再启动 Nginx 服务

    nginx

如果你的 Nginx 已经启动了的话，使用
   
    nginx -s reload 重启 Nginx

访问测试

浏览器访问http://127.0.0.1:8080/info.php 来看看刚刚新建的测试文件是否解析了：

哇哦~ok

## Nodejs

Node.js 是能够在服务器端运行 JavaScript 的开放源代码、跨平台 JavaScript 运行环境。

### 安装 Nodejs

nodejs-lts 是长期支持版本，如果执行 pkg install nodejs 版本后，发现 npm 报如下错误:

    segmentation fault

那么这个时候可以尝试卸载当前版本 
    
    pkg uninstall nodejs 

然后执行下面命令安装长期稳定版本:

    pkg install nodejs-lts

安装完成后使用如下命令查看版本信息：

    node -V
    npm -V

## Hello World

新建一个 hello.js 脚本，内容如下:

    console.log('Hello Termux');

然后尝试运行:

    $ node hello.js
    Hello Termux

## http-server

http-server 是一个基于 Node.js 的简单零配置命令行HTTP服务器。

    # 安装 http-server
    npm install -g http-server

    # 运行 http-server
    http-server

尝试电脑端浏览器直接访问看看:

OK

### 安装报错

早期版本的 Termux 的 npm 安装一些包的时候会报如下错误：

    Cannot read property 'length' of undefined

查了下是这边版本的问题

新版本貌似npm正常

这是一个BUG，官方的解决方法如下：

    disable concurrency in case of libuv/libuv#1459

编辑如下文件：

    vim $PREFIX/lib/node_modules/npm/node_modules/worker-farm/lib/farm.js

我这里修改length的是4，这个好像和CPU有关，总之这里的 length 得指定一个数字。

新版本貌似npm正常

然后在重新安装下
   
    npm install hexo-cli -g

成功。

## PHP

PHP 是一种开源的脚本语言，适用于网络开发。语法借鉴吸收C语言、Java 和 Perl 等流行计算机语言的特点，易于学习，PHP 是世界上最好的语言（手动狗头）。

### 安装PHP

Termux 官方封装了 PHP，所以我们安装起来就很方便：

    pkg install php

安装完成后查看下版本信息：

    php --version

运行测试文件

自 PHP5.4 之后 PHP内置了一个 Web 服务器。在 Termux 下可以很方便地测试 PHP 文件

首先在家(~)目录下建一个www 文件夹，然后在www文件夹下新建一个index.php文件，内容为：

    <?php phpinfo();?>

完整的步骤如下:

    # 新建 www 文件夹
    mkdir ~/www

    # 创建 inedx.php 文件
    echo '<?php phpinfo();?>' > ~/www/index.php

编写完成index.php文件后，尝试使用 PHP 内置的 WebServer 直接启动:

    # 进入家目录
    cd ~

    # 启动 WebServer
    php -S 0.0.0.0:8888 -t www/

自己制定端口后，浏览器访问http://127.0.0.1:8888效果如下：

## Python

Python是近几年非常流行的语言，Python 相关的书籍和资料也如雨后春笋一般不断涌现，带来了活跃了 Python 学习氛围。

### 安装python2

Python2 版本要淘汰了，大家简单了解一下就好：

    pkg install python2 -y

安装完成后，使用python2命令启动 Python2.7 的环境

### 安装python3

Termux 安装 Python 默认版本是 Python3 的版本，与此同时也顺便安装了clang

    pkg install python -y

安装完成后，查看下clang和Python的版本

注意版本区分

如果你同时安装了 Python3 和 Python2 版本的话，最好验证一下各个版本情况，做到心知肚明，我是先安装 Python3 然后再安装 Python2的

升级pip版本

pip 保持最新是一个好习惯，升级方式很简单：

    # 升级 pip2 

    python2 -m pip install --upgrade pip -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

### 升级 pip3

    python -m pip install --upgrade pip -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

这两条命令分别升级了pip2和pip3到最新版。升级完成后你会惊讶的发现你的pip3命令不见了？？？然后这个时候就开始吐槽国光了（内心OS：国光 非要强迫症升级 pip 版本，这下好了吧！）

不要慌 问题不大，我们可以手动查看当前有哪些可执行的 pip 文件，使用如下命令：

    ls /data/data/com.termux/files/usr/bin|grep pip

原来我们的pip3变成了pip3.8了啊

接下来分别查看对应 pip 可执行文件的版本

现在全都是最新版的 pip 了哦

## iPython

iPython是一个 Python 的增强版本的交互式 shell，支持变量自动补全，自动缩进，支持shell命令等，内置了许多很有用的功能和函数。iPython 可以提高我们的学习效率！

先安装clang,否则直接使用pip安装ipython会失败报错. 没有安装的话使用 pkg install clang安装

    # -i 手动指定国内清华 pip 源 提高下载速度
    pip install ipython -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
    pip3.8 install ipython -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

执行完上述命令分别安装好对应版本的iPython后，然后分别查看对应版本信息：

    ipython2 -V
    ipython -V

## Jupyter Notebook

Jupyter Notebook（此前被称为 iPython notebook）可以在 Web 端提供Python交互，虽然和iPython共享同一个内核，但是更强大。

Jupyter notebook 相关的依赖比较多 安装起来较为耗时 国光就只用 Python3 版本来演示了，另外请务必要使用国内的 pip 源来安装

下面官方建议安装的完整的命令：

    pkg update
    pkg install proot
    termux-chroot
    apt install git clang
    apt install pkg-config
    apt install python python3-dev 
    apt install libclang libclang-dev
    apt install libzmq libzmq-dev
    apt install ipython 
    pip install jupyter 

如果你一步步跟着本文安装顺序操作的话，发现很多工具我们都安装过了(我真的有先见之明…)，那么直接参考如下命令安装即可:

    # -i 手动指定国内中清华 pip 源 提高下载速度
    # 更新是个好习惯
    pkg update

    # 切换模拟的 root 环境
    termux-chroot

    # 安装相关依赖
    pkg install libclang

    # 安装 jupyter
    pip3 install jupyter -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

    # 安装完成退出 chroot
    exit

    # 安装 jupyterlab
    pip3 install jupyterlab -i https://pypi.tuna.tsinghua.edu.cn/simple some-package

安装好之后查看一下版本信息：

    jupyter --version

所有插件均安装完成

Jupyter Notebook就安装好了，这个比较强大更详细的教程大家可以自行去谷歌或者百度一下，国光这里只演示基本的功能。

先启动 notebook

    jupyter notebook

然后会看到运行的日志，我们复制出提示的URL


复制出的这个URL地址 在浏览器中打开


就成功运行了，那我们按照提示走个形式，输出个 Hello World就跑路：


OK 运行成功，那么回到 Termux 里面使用组合键 Ctrl + C -> 中止当前的 Jupyter 进程

# 网站搭建

网站搭建这一块实际上原理是大同小异的，国光这里只写几个网站的安装方法，给大家提供一个思路。

## DVWA

DVWA 是一个用来搞 Web 安全从业者入门使用的一个练习靶场，用来学习掌握基本的漏洞原理使用的，如果你对 Web 安全不感兴趣的话可以直接跳过这一个小节。

这里建议 DVWA 练习的时候 要结合源码去分析漏洞 不要直接把网上攻击流程走一步就草草了之了 不看源码的学习 等于啥都没有学

环境准备

因为 DVWA 靶场是 PHP编写的，所以你需要 提前配置好 Nginx 、PHP 以及 数据库，关于这方面配置可以参考前面开发环境下分类的「Nginx」、「MariaDB(MySQL)」和 「Nginx 解析 PHP」章节

下载 DVWA

    wget https://github.com/ethicalhack3r/DVWA/archive/master.zip

如果访问 Github 比较慢的话，可以尝试如下链接:

    wget https://hub.fastgit.org/ethicalhack3r/DVWA/archive/master.zip

解压到 Nginx 目录下

    # 解压
    unzip master.zip -d $PREFIX/share/nginx/html/

    # 重命名
    cd $PREFIX/share/nginx/html/
    mv DVWA-master dvwa

### 新建数据库

    mysql -uroot -p*** -e"create database dvwa;show databases;"
    *** 这里是mysql的密码

可以看到 dvwa 数据库已经新建成功了。

### 编辑 DVWA 配置文件

    # 将配置文件 还原为 PHP 后缀
    cd $PREFIX/share/nginx/html/dvwa/config
    mv config.inc.php.dist config.inc.php

    # 编辑配置文件
    vim mv config.inc.php.dist config.inc.php

初次访问测试网站

按照上述配置好 DVWA 之后，浏览器访问: http://192.168.31.124:8080/dvwa/setup.php

可以看到 allow_url_include 运行 URL 远程包含没有开启，我们得手动开启一下:

实际上正常人是不会去开启这个的，十分危险，但是 DVWA 是一个靶场，有些漏洞实际上就是利用 PHP 配置不当造成的，这样才让新手有攻击下来的信心。

### 配置 php.ini

Termux 下默认是没有 php.ini 文件的，不信我们手动来查找一下:

    php --ini

    Configuration File (php.ini) Path: /data/data/com.termux/files/usr/lib
    Loaded Configuration File:         (none)
    Scan for additional .ini files in: (none)
    Additional .ini files parsed:      (none)

发现 php.ini 的文件应该存放在:

    /data/data/com.termux/files/usr/lib 目录下，但是 PHP 没有找到配置文件，所以需要我们手动在这个目录下新建 php.ini 配置文件:

    echo 'allow_url_include = On' > $PREFIX/lib/php.ini

注意这是一个不安全的配置 只是为了配合本地的 DVWA 靶场 做模拟黑客攻击练习使用的

配置完成后，自己尝试使用php --ini来定位搜索配置文件，会发现 PHP 已经找到了配置文件了。

修改完配置文件后 得重启 php-fpm 服务:

    # 杀掉 php-fpm 相关的进程
    kill -9 `pgrep fpm`

    # 再次启动 php-fpm
    php-fpm

再次访问测试网站:

浏览器访问: http://192.168.31.124:8080/dvwa/setup.php

可以看到刚刚的配置文件生效了，现在安全检查全部通过

既然 安全检查通过的话，那么就直接页面滚动到最下面直接点击 Create/Reset Database初始化数据库按钮即可，初始化成功后会自动跳转到登录界面。

DVWA 默认的用户有5个，用户名密码如下：

    用户名	密码
    admin	password
    gordonb	abc123
    1337	charley
    pablo	letmein
    smithy	password
 
登录成功!!!!

## Hexo

Hexo 是一个用 Nodejs 编写的快速、简洁且高效的博客框架。Hexo 使用 Markdown 解析文章，在几秒内，即可利用靓丽的主题生成静态网页。另外大家看到我的博客就是使用 Hexo 搭建的哦。

### 安装 Hexo

Hexo 是用 Nodejs 编写的，所以安装的话得使用 npm 命令来安装：

    npm install hexo-cli -g

安装完成的话，顺便看一下 Hexo 相关的版本信息吧：

    hexo -v

### Hexo 基本部署

我们建立一个目录，然后到这个目录下初始化Hexo 环境

    # 手动创建一个目录
    mkdir hexo  

    # 进入目录下并初始化Hexo环境
    cd hexo  
    hexo init  

    #生成静态文件 启动Hexo
    hexo g
    hexo s      


然后就跑起来一个最基本的 Hexo 博客，关于 Hexo 博客的详细教程，建议搭建去参考Hexo官方文档，我这里重点在于 Termux 其他的不作过多的叙述.
使用浏览器访问: http://127.0.0.1:4000 即可看到 Hexo

## Hexo 部署到 Nginx

Hexo 是纯静态博客，官方默认把 Hexo 搭建在 Github Pages 仅仅是把 Hexo 根目录的 public 文件夹即 Hexo 生成的纯 HTML 源码部署到上面而已。所以知道这样原理 我们就可以轻而易举地将 Hexo 部署到 Nginx 下面。

生成 HTML 纯静态源码

    hexo g

可以看到 Hexo 的根目录下 已经生成了 public 文件夹了

拷贝源码搭到 Nginx

现在我们只需要将 public 的文件夹里面的源码 全部拷贝到 Nginx 的网站根目录下：

    # 在 nginx 根目录下新建 hexo 文件夹
    mkdir $PREFIX/share/nginx/html/hexo

    # 拷贝 源码到 nginx 下
    cp -rf public/* $PREFIX/share/nginx/html/hexo

访问效果查看

浏览器访问:http://127.0.0.1:8080/hexo/ 即可看到效果

当然这里网站的CSS等样式没有加载出来，这个原因是 Hexo 对网站目录下部署并不友好 ，大概有如下解决方法：

Nginx vhosts 配置多域名，这个服务器上常用的操作，但是 Termux 里面实现难度较高
将 Hexo 的源码 直接拷贝到 Nginx 的根目录下，不用拷贝到 html/hexo 目录下了，然后直接访问 http://127.0.0.1:8080 即可看到效果
这里就只是说一下这个思路，因为强迫症的我 不能忍受 Nginx 根目录的文件 乱七八糟 =，= 大家想尝试的话 按照我这个思路去尝试就可以了

## knifefire还会持续更新文章的啦

©knifefire & ZH
