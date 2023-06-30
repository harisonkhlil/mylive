# Mac 默认设置

## 删除 .DS_store

**打开终端输入以下禁止.DS_store生成的代码：**

```shell
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool TRUE
```

**恢复.DS_store生成:**

```shell
defaults delete com.apple.desktopservices DSDontWriteNetworkStores
```



## 让 Finder 显示完整路径

Finder 默认的标题栏只显示当前目录的名字,即可让 Finder 在顶部显示文件目录的完整路径。

```shell
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
```

