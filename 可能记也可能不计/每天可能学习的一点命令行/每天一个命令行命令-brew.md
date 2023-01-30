# 每天一个命令行命令-brew

## Install

`/bin/bash -c "$(curl -fsSL` [`https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh`](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)`)"`

一些进阶命令

```bash
brew doctor #诊断依赖冲突等
brew home git #打开 git 包的主页
brew info git #查看包信息
brew deps git #查看 git 的依赖
brew --cached #查看缓存路径
brew --prefix #查看安装目录
brew cleanup -n         # 查看可清理的旧版本包
brew deps --installed --tree #查看已经安装的包用数
```



## 可能未来会进来补充新功能
