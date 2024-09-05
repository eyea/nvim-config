# NeoVim 安装配置

## 环境说明
```
➜  ~ sw_vers
ProductName:		macOS
ProductVersion:		14.2.1
BuildVersion:		23C71
```

## 安装 neovim

```bash
brew install neovim
````
[更多的安装方式](https://github.com/neovim/neovim/blob/master/INSTALL.md)

## 复制文件
将 __init.vim__，放置在 __~/.config/nvim/__ 目录下，此 __init.vim__ 中添加了自动 __install vim-plug__ 的检查脚本：


##  安装插件
打开 __iterm2__ 执行命令 __nvim__

```bash
nvim
```

打开的界面输入
```bash
:PlugInstall
```

等待安装，与此同时，新开个终端界面，安装字体：__Nerd Fonts__ (下面是把所有字体都下载了，换着体验吧)

```bash
brew tap homebrew/cask-fonts
brew search nerd
brew install --cask font-hack-nerd-font 
brew install homebrew/cask-fonts/font-robotomono-nerd-font-mono
brew install --cask font-3270-nerd-font  
brew install --cask font-fira-mono-nerd-font  
brew install --cask font-inconsolata-go-nerd-font  
brew install --cask font-inconsolata-lgc-nerd-font  
brew install --cask font-inconsolata-nerd-font  
brew install --cask font-monofur-nerd-font  
brew install --cask font-overpass-nerd-font  
brew install --cask font-ubuntu-mono-nerd-font  
brew install --cask font-agave-nerd-font  
brew install --cask font-arimo-nerd-font
brew install --cask font-anonymice-nerd-font
brew install --cask font-aurulent-sans-mono-nerd-font
brew install --cask font-bigblue-terminal-nerd-font
brew install --cask font-bitstream-vera-sans-mono-nerd-font
brew install --cask font-blex-mono-nerd-font
brew install --cask font-caskaydia-cove-nerd-font
brew install --cask font-code-new-roman-nerd-font
brew install --cask font-cousine-nerd-font
brew install --cask font-daddy-time-mono-nerd-font
brew install --cask font-dejavu-sans-mono-nerd-font
brew install --cask font-droid-sans-mono-nerd-font
brew install --cask font-fantasque-sans-mono-nerd-font
brew install --cask font-fira-code-nerd-font
brew install --cask font-go-mono-nerd-font
brew install --cask font-gohufont-nerd-font
brew install --cask font-hack-nerd-font
brew install --cask font-hasklug-nerd-font
brew install --cask font-heavy-data-nerd-font
brew install --cask font-hurmit-nerd-font
brew install --cask font-im-writing-nerd-font
brew install --cask font-iosevka-nerd-font
brew install --cask font-jetbrains-mono-nerd-font
brew install --cask font-lekton-nerd-font
brew install --cask font-liberation-nerd-font
brew install --cask font-meslo-lg-nerd-font
brew install --cask font-monoid-nerd-font
brew install --cask font-mononoki-nerd-font
brew install --cask font-mplus-nerd-font
brew install --cask font-noto-nerd-font
brew install --cask font-open-dyslexic-nerd-font
brew install --cask font-profont-nerd-font
brew install --cask font-proggy-clean-tt-nerd-font
brew install --cask font-roboto-mono-nerd-font
brew install --cask font-sauce-code-pro-nerd-font
brew install --cask font-shure-tech-mono-nerd-font
brew install --cask font-space-mono-nerd-font
brew install --cask font-terminess-ttf-nerd-font
brew install --cask font-tinos-nerd-font
brew install --cask font-ubuntu-nerd-font
brew install --cask font-victor-mono-nerd-font

```

安装完后，在 终端的 settings > Profiles > Text > Font 选择上面的其中一个字体，当然可以选择别的~

目前用的是 __Hack Nerd Font Propo__

## 核心配置

- 字体安装：下载`Nerd Fonts`后，通过 Mac & Windows 系统功能安装字体，在`iTerm2`或`Terminal(WSL)`中选择即可，NeoVim 中无需字体相关配置。
- Leader Key：`let g:mapleader = ","`
- ESC 映射：`imap jj <esc>`

## 插件选择

- `Plug 'rakr/vim-one'`     主题插件
- `Plug 'vim-airline/vim-airline'`    状态栏主题
- `Plug 'ryanoasis/vim-devicons'`   炫酷图标，依赖 Nerd Fonts
- `Plug 'luochen1990/rainbow'`      括号彩色匹配
- `Plug 'kana/vim-fakeclip'`        拉齐各平台复制粘贴，使用时屏蔽默认，完全隔离Vim和系统剪贴板
- `Plug 'neoclide/coc.nvim', {'branch': 'release'}`    自动补全神器
- `Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }`   文件模糊查找
- `Plug 'junegunn/fzf.vim'`    文件模糊查找
- `Plug 'voldikss/vim-floaterm'`   Float terminal
- `Plug 'mattn/emmet-vim'` HTML 快速补全
- `Plug 'ervandew/supertab'`     Tab功能增强，使用Tab键补全选择等
- `Plug 'tpope/vim-commentary'`  自动注释插件
- `Plug 'ntpeters/vim-better-whitespace'` 清除行末空格
- `Plug 'justinmk/vim-sneak'`  光标快速移动

## 使用提示
1. 当使用 `Plug 'voldikss/vim-floaterm'`，你会看到本配置文件中有 `nmap <leader>lz :FloatermNew lazygit<cr>`
该行指令，很明显需要有 `lazygit`的执行环境： [lazygit install](https://github.com/jesseduffield/lazygit?tab=readme-ov-file#homebrew)
同时也需要在 `git`的仓库内执行

2. `Plug 'mattn/emmet-vim'` 自动补充，快捷键是 `control + y + ,` 更多使用说明看 [mattn/emmet-vim](https://github.com/mattn/emmet-vim?tab=readme-ov-file#quick-tutorial)
3. `Plug 'ervandew/supertab'` Supertab is a vim plugin which allows you to use <Tab> for all your insert completion needs (:help ins-completion). [ervandew/supertab](https://github.com/ervandew/supertab)
4. `Plug 'tpope/vim-commentart` 注释 比如 `vmap gc` `nmap <leader>cc` [tpope/vim-commentary](https://github.com/tpope/vim-commentary)
5. `Plug 'ntpeters/vim-better-whitespace'` This plugin causes all trailing whitespace characters (see Supported Whitespace Characters below) to be highlighted. [ntpeters/vim-better-whitespace](https://github.com/ntpeters/vim-better-whitespace)
6. `Plug 'justinmk/vim-sneak'` 使用 `:help sneak` Jump to any location specified by two characters. [justinmk/vim-sneak](https://github.com/justinmk/vim-sneak)
7. `Plug 'preservim/nerdtree'` A file system explorer for the Vim editor. [preservim/nerdtree](https://github.com/preservim/nerdtree) 我这里打开显示文件行数的功能

