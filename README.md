# Mac OS X Dev Setup

这篇文章主要介绍我怎么快速搭建开发环境在新的Mac。我会安装PHP环境为例为你介绍详细的流程。

如果你并不是php开发者，那下面介绍的其他的App或许也会对你有帮助。你可以边阅读边试着感受一下。

这边文档的操作假设在你的新Mac环境进行的。如果你有任何好的想法和建议，欢迎和我联系[Twitter](https://twitter.com/JustinDxtan)。



1. 去掉Dock上不常用的App，保留Finder，启动台，Safari浏览器。
2. 打开设置：
   - 通用>使用暗色菜单栏和程序坞。
   - 程序坞>自动显示和隐藏程序坞.。
3. 下载[Chrome](https://www.google.com/chrome/),我们直接安装完成，然后去掉Dock里面的Safari浏览器。
4. 下载Apps:
 - [Dropbox](https://www.dropbox.com)
 - [1Password](https://1password.com/)
 - [Alfred](https://www.alfredapp.com/)
 - [Contexts](https://contexts.co/)
 - [Sublime text 3](https://www.sublimetext.com/)
5. 安装Dropbox,登陆自己的帐号。然后安装1Password,密码文件可以关联保存在dropbox里面。

6. 安装Alfred,完成后打开 设置>键盘>快捷键>聚焦，去掉勾选 "显示聚焦搜索"和“显示Finder搜索窗口”，Alfred 打开快捷键设置为Option+空格。

7. 安装Contexts,打开设置>安全与隐私>辅助功能>勾选Contexts 。

8. 安装sublime，安装包管理[PackageControl](https://packagecontrol.io/installation). 然后安装喜欢的主题[Material Theme](https://github.com/equinusocio/material-theme)。

   - 使用命令行程序,先创建链接：

     `$ ln -s /Application/Sublime\ Text.app/Contents/ShareSupport/bin/subl /usr/local/bin/subl `

   - 然后只用一下命令就可以使用Sublime Text打开当前文件夹。

     `$ subl .`

     

9. 安装[Source code pro](https://github.com/adobe-fonts/source-code-pro/tags )字体,下载后打开安装包内的OTF文件夹，全选里面的字体，安装。

10. 下载安装[Iterm2](https://www.iterm2.com/),，安装完成后打开:

  - 安装xcode扩展,输入

    `$ xcode-select —install `

  - 继续安装[Homebrew](https://brew.sh)

    `$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

  - 使用[oh-my-zsh](http://ohmyz.sh/)

    `$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

  - 设置常用的快捷键, 打开iterm2设置>profiles>keys ，点击加号进行添加:

    - cmd+右 /send Hex Code /0x05 `使用cmd+右 跳转到一行命令的最右边`
    - cmd+ 左 /send Hex Code /0x01 `使用cmd+左 跳转到一行命令的最左边`
    - option+右 /send Escape Sequence /Esc+f  `使用option+右 跳转到的前一个命令词语的最右边`
    - option + 左 /Excape Sequence /Esc + b `使用option+左 跳转到的后一个命令词语的最左边`
    - cmd+delete /send Hex code /0x15 `强制清除当前行输入的明亮`

11. 下载安装[Vagrant](https://www.vagrantup.com/) 和[VirtualBox](https://www.virtualbox.org/)，可以搭建本地虚拟开发环境。

12. 安装Git,Mac系统安装完xcode-select后，git会默认安装好了,但是版本不是最新的。

    -  `$ git —version`来显示当前的git版本，通常会显示`git version 2.15.1 (Apple Git-101)`,是苹果自带的版本。
    - `$ which git`,默认的git执行文件在`/usr/bin/git`。
    - 所以我们使用brew安装最新版的`$ brew install git`。
    - 安装完成后，再次查看版本`$ git --version`，会发现还是之前的版本.
    - 所以我们移动默认的git文件,`$ mv /usr/bin/git /usr/bin/git-apple`, 这样就会执行brew安装后的git了。

13. 安装开发常用的App

    - [Sequel pro](https://www.sequelpro.com/) 简单的Mysql管理工具。
    - [Path Finder](https://cocoatech.com/#/)在Finder工具栏下面显示面包屑，可以快速打开上层文件夹。
    - [Transmit](https://panic.com/transmit/)最好用的FTP工具。
    - [Tower](https://www.git-tower.com/mac/)我最喜欢的用的，它是一个可视化版本控制管理工具，在国外非常受欢迎。
    - [Telegram](https://telegram.org/)团队协作聊天工具。
    - [Textual](https://www.codeux.com/textual/)它是国外比较受欢迎的简单的

14. 安装PHP开发环境:

    - `$ brew update`
    - `$ brew install wget php71 mysql sqlite composer php71-redis` 
    - `$ composer global require laravel/valet`
    - `$ valet install`