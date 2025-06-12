# 安装Homebrew

安装 homebrew：

```bash
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

常用命令（以下命令以对 git 操作为例）：

- brew -v                 查看 homebrew 安装版本
- brew --help             简洁命令帮助
- man brew                完整命令帮助
- brew search git         搜索软件包
- brew install git        安装软件包
- brew uninstall git      卸载安装包
- brew list               显示已安装的所有软件包
- brew list git           查看安装软件包的安装地址
- brew pin git            锁定不想更新的软件包
- brew unpin git          取消锁定不想更新的软件包
- brew outdated           查看已安装的哪些软件包需要更新以及更新情况
- brew update             同步远程最新更新情况，对本机已经安装并有更新的软件用*标明
- brew upgrade git        更新单个软件包
- brew info git           查看软件包信息
- brew home git           访问软件包的官方网站
- brew cleanup -n         查看可清理的旧版本包，不执行实际操作
- brew cleanup            清理所有已安装软件包的历史版本
- brew cleanup git        清理单个已安装软件包的历史版本

homebrew 目录结构：

- /opt/homebrew/Cellar       所有 homebrew 安装的程序，都以[程序名/版本号]存放于本目录下
- /opt/homebrew/bin          用于存放所有安装程序的启动链接（相当于快捷方式）
- /opt/homebrew/etc          安装程序的配置文件默认存放路径
- /opt/homebrew/opt          homebrew 下载软件包存放路径

# 解决每次需要加 sudo 赋权限的问题

```bash
# 将文件夹的所有者更改为您当前的用户
sudo chown -R $(whoami) 文件夹路径

# 固定赋权限
sudo chown -R $(whoami) /Users/longyuhuan/Documents/BackEndWorkspace
sudo chown -R $(whoami) /Users/longyuhuan/Documents/FrontEndWorkspace
sudo chown -R $(whoami) /Users/longyuhuan/Documents/TyporaWorkspace
sudo chown -R $(whoami) /Users/longyuhuan/.npm/*
```

