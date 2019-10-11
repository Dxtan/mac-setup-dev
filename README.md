# Mac OS X Dev Setup

这篇文章主要介绍我怎么快速搭建开发环境在新的Mac。我会安装PHP环境为例为你介绍详细的流程。

如果你并不是php开发者，那下面介绍的其他的App或许也会对你有帮助。你可以边阅读边试着感受一下。

这边文档的操作假设在你的新Mac环境进行的。如果你有任何好的想法和建议，欢迎和我联系[Twitter](https://twitter.com/JustinDxtan)。



## System preferences

去掉Dock上不常用的App，保留Finder，启动台，Safari浏览器。

1. 打开设置：
   - 通用>使用暗色菜单栏和程序坞。
   - 程序坞>自动显示和隐藏程序坞。
   - 触控板>勾选【轻点开点按】
   - 键盘>键盘, 把【按键重复】拖到最右边，调整到最快。
   - 键盘>键盘, 把【重复前延迟】拖到最右边，调整到最快。
   - 键盘>快捷键,选中左边的输入法，然后修改【选择上一个输入法】的快捷键为`cmd+空格`
   - 辅助功能>鼠标与触控板>触控板选项>启用拖移
## Chrome

1. 下载[Chrome](https://www.google.com/chrome/),我们直接安装完成，然后去掉Dock里面的Safari浏览器。
#### Chrome Web App

- [AdBlock](https://chrome.google.com/webstore/detail/adblock/gighmmpiobklfepjocnamgkkbiglidom)
- [Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop)
- [PHPView](https://chrome.google.com/webstore/detail/phpview/nlkobfbkblfhlcobdomlhmpbbhmcbkfd)
- [Vue.js devtools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
- [划词翻译](https://chrome.google.com/webstore/detail/%E5%88%92%E8%AF%8D%E7%BF%BB%E8%AF%91/ikhdkkncnoglghljlkmcimlnlhkeamad)

## Apps Download

 - [Dropbox](https://www.dropbox.com)
 - [1Password](https://1password.com/)
 - [Alfred](https://www.alfredapp.com/)
 - [Sublime text 3](https://www.sublimetext.com/)
 - [PhpStorm](https://www.jetbrains.com/phpstorm/)
 - [Dash](https://kapeli.com/dash)
 - [iTerm2](https://www.iterm2.com/)
 - [Vagrant](https://www.vagrantup.com/) 
 - [VirtualBox](https://www.virtualbox.org/)

## Dropbox

1. 安装Dropbox,登陆自己的帐号。然后安装1Password,密码文件可以关联保存在dropbox里面。

## Alfred

1. 安装Alfred,完成后打开 设置>键盘>快捷键>聚焦，去掉勾选 "显示聚焦搜索"和“显示Finder搜索窗口”，Alfred 打开快捷键设置为Option+空格。

## Sublime Text

1. 安装sublime，安装包管理[PackageControl](https://packagecontrol.io/installation). 然后安装喜欢的主题[Material Theme](https://github.com/equinusocio/material-theme)。

   - 使用命令行程序,先创建链接：

     `$ ln -s /Application/Sublime\ Text.app/Contents/ShareSupport/bin/subl /usr/local/bin/subl `

   - 然后只用一下命令就可以使用Sublime Text打开当前文件夹。

     `$ subl .`

2. 安装[Source code pro](https://github.com/adobe-fonts/source-code-pro/tags )字体,下载后打开安装包内的OTF文件夹，全选里面的字体，安装。

3. 我的Sublime个人偏好设置在[sublime-user-profile](https://github.com/Dxtan/sublime-user-profile)

## PhpStorm

下载安装最新版的[PhpStorm](https://www.jetbrains.com/phpstorm/)，安装完成。

> 我个人喜欢使用[PhpStorm 2016.2](http://download.jetbrains.com/webide/PhpStorm-2016.2.2.dmg), 因为这个版本之后，输入的光标高度不是满行，用起来很不舒服。

PhpStorm是一个非常强大的编译器，当然如果你想使用的顺畅，必须学会怎么设置它，关于PhpStorm

的设置我单独用一篇[文档](./phpstorm-settings.md)来具体说明。

## iTerm2

1. 下载安装[iTerm2](https://www.iterm2.com/)，安装完成后打开:

  - 安装xcode扩展,输入

    `$ xcode-select —install `

  - 继续安装[Homebrew](https://brew.sh)

    `$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

  - 使用[oh-my-zsh](http://ohmyz.sh/)

    `$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

  - 配置zsh插件,

```shell
    $ brew install autojump
  
    $ git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  
    $ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    
    $ vim ~/.zshrc
    
    plugins=(git autojump zsh-autosuggestions zsh-syntax-highlighting)
  
```

  - 设置常用的快捷键, 打开iterm2设置>profiles>keys ，点击加号进行添加:
  
    - cmd+右 /send Hex Code /0x05 `使用cmd+右 跳转到一行命令的最右边`
    - cmd+ 左 /send Hex Code /0x01 `使用cmd+左 跳转到一行命令的最左边`
    - option+右 /send Escape Sequence /Esc+f  `使用option+右 跳转到的前一个命令词语的最右边`
    - option + 左 /Excape Sequence /Esc + b `使用option+左 跳转到的后一个命令词语的最左边`
    - cmd+delete /send Hex code /0x15 `强制清除当前行输入的明亮`

- iTerm2 全屏后无法保持透明的问题,设置preference>general> 不勾选 "Native full screen windows",  然后修改背景色透明度`Profiles>Window>Transarency`

- 在任意终端中输入`open .`即可默认打开 Finder 显示当前的目录

- iTerm2可以自定义设置界面的，推荐我个人自定义的界面，喜欢的可以下载项目里面[com.googlecode.iterm2.plist](https://github.com/Dxtan/mac-setup-dev/blob/master/com.googlecode.iterm2.plist)后导入就可以了。


## Vim

下载项目里面的[.vimrc](https://github.com/Dxtan/mac-setup-dev/blob/master/.vimrc)，放在用户根目录:

```bash
syntax enable //语法高亮显示
colorscheme desert //命令行显示不同的文件类型会有不同的颜色

"-------------General Settings--------------"
set backspace=indent,eol,start           "Make backspace behave like every other editor.
let mapleader = ',' 		       "The default leader is \, but a comma is much better.
set number					"Let's activate line numbers.
set linespace=15   		     "Macvim-specific line-height.


"-------------Search--------------"
set hlsearch
set incsearch


"-------------Mappings--------------"
"Add simple highlight removal.
nmap <Leader><space> :nohlsearch<cr>

"-------------Auto-Commands--------------"

"Automatically source the Vimrc file on save.
augroup autosourcing
	autocmd!
	autocmd BufWritePost .vimrc source %
augroup END
```

## Vagrant

1. 下载安装[Vagrant](https://www.vagrantup.com/) 和[VirtualBox](https://www.virtualbox.org/)，可以搭建本地虚拟开发环境

## Git

1. 安装Git,Mac系统安装完xcode-select后，git会默认安装好了,但是版本不是最新的。

   -  `$ git —version`来显示当前的git版本，通常会显示`git version 2.15.1 (Apple Git-101)`,是苹果自带的版本。
   -  `$ which git`,默认的git执行文件在`/usr/bin/git`。
   -  所以我们使用brew安装最新版的`$ brew install git`。
   -  安装完成后，再次查看版本`$ git --version`，会发现还是之前的版本.
   -  所以我们移动默认的git文件,`$ mv /usr/bin/git /usr/bin/git-apple`, 这样就会执行brew安装后的git了。如果提示没有权限，重启系统就好了。

2. Git的基本设置:

   `$ git config --global user.name "xxx"`设置Git用户名

   `$ git config --global user.email "xxx@mail.com"`设置Git邮箱

   `$ git config --list` 查看所有的配置

   `$ ssh-keygen`生成ssh key用户Git仓库SSH权限。

3. 如果你喜欢命令行操作Git的话，有一个快捷键方式查看日志非常不错。

   `alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"`

   在`~/.zshrc`最后一行添加这个，会让Git日志变得更美观.


## Dev  environment

#### Install PHP

- `$ brew update`
- `$ brew install wget php@7.3 mysql nginx sqlite composer php-cs-fixer` 
- `$ pecl install xdebug`

 > 这样安装以后可能会安装php扩展比较麻烦，因为很早的homebrew-php被合并到homebrew-core里面了，扩展安装必须通过pecl安装，然后修改php.ini打开扩展，php手册里面也有[说明](http://php.net/manual/zh/mongodb.installation.homebrew.php)。
 > 所以我保留了早期的[homebrew-php](https://github.com/Dxtan/homebrew-php/import)工程，只要放在`/usr/local/Homebrew/Library/Taps/homebrew` 目录下面，一样可以安装php7.1,7.2,扩展也可以通过brew安装.

#### Composer

composer对PHP开发来说还是非常重要的，在[https://packagist.org/](https://packagist.org/)提供了很多的依赖包。

当然，国内需要设置一下镜像源：

`$ composer config -g repo.packagist composer https://packagist.phpcomposer.com`

通常我喜欢用[Laravel/valet](https://laravel.com/docs/5.6/valet)快速搭建web环境。

`$ copmoser global require laravel/valet && valet install`

还有laravel安装程序：

`composer global require laravel/installer`



## Other Apps

1. 开发常用的App

   - [Sequel pro](https://www.sequelpro.com/) 简单的Mysql管理工具。
   - [Transmit](https://panic.com/transmit/)最好用的FTP工具。
   - [Tower](https://www.git-tower.com/mac/)我最喜欢的用的，它是一个可视化版本控制管理工具，在国外非常受欢迎。
   - [Github Desktop](https://desktop.github.com)github开源可视化版本控制管理工具，界面简洁。
   - [Telegram](https://telegram.org/)团队协作聊天工具。
   
2. 提高工作效率App

   - [CleanMyMac 3](https://macpaw.com/cleanmymac)
   - [Alternote](http://alternoteapp.com/)
   - [Bee](https://www.neat.io/bee/)
   - [Noizio](http://noiz.io/)
   - [Trello](https://trello.com/)
   - [Typora](https://typora.io/)
   - [VEEER](https://veeer.io/)
   - [Droplr](https://droplr.com/)





> 文档版权所有，未经许可不得转载流传，谢谢合作