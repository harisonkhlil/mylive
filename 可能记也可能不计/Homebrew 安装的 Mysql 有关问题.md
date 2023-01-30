# Homebrew 安装的 Mysql 有关问题

安装方法 `brew install mysql`

```other
# 设置密码
We've installed your MySQL database without a root password. To secure it run:
    mysql_secure_installation

MySQL is configured to only allow connections from localhost by default
# 连接
To connect run:
    mysql -uroot
# 后台启动
To have launchd start mysql now and restart at login:
  brew services start mysql
# 简单启动
Or, if you don't want/need a background service you can just run:
  mysql.server start
```

> mysql_secure_installation:: as follows

```other
# 输入root用户密码
Securing the MySQL server deployment.
# 使用空白密码连接（这里表示当前的连接状态）
Connecting to MySQL using a blank password.

# 验证密码组件可用于测试密码并提高安全性。它检查密码的强度并允许用户仅设置以下密码足够安全。您想设置“验证密码”组件吗？
VALIDATE PASSWORD COMPONENT can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD component?
 
Press y|Y for Yes, any other key for No: 这里选y
# 密码验证策略分为三个级别
There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 这里选0即可设置简单密码

# 请在此处设置root密码。
Please set the password for root here.
New password: 第一次输入密码
Re-enter new password: 重输入一次确认

# 删除匿名用户？
Remove anonymous users? (Press y|Y for Yes, any other key for No) : 我选y，其他的我没试过

# 禁止远程登录
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : 我选y，因为我只在笔记本使用

# 是否删除测试库
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : 我选y，其他的我没试过

# 现在重新加载特权表
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : 我选y，其他的我没试过
```

尽量不要设置开启启动,如果要设置开机自启动按照以下:

```ruby
# 设置开机自启
# 1. 首先确认该目录是否存在，若已经存在不用执行本命令  
$ mkdir -p ~/Library/LaunchAgents   

# 2. 从mysql的安装目录下`/usr/local/Cellar/mysql/8.0.19`找到`homebrew.mxcl.mysql.plist`文件，并复制到～/Library/LaunchAgents目录下

# 3. 执行命令
$ launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist

# 关闭开机自启
# 1. 执行命令
$ launchctl unload -w ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
# 2. 删除
$ rm -f ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
```

一些普通命令

```other
# 后台启动
brew services start mysql
# 启动
mysql.server start

# 连接
mysql -uroot -p

# 停止
mysql.server stop

# 重启
mysql.server restart
```

卸载 Mysql  `brew uninstall mysql && brew cleanup`

\#mysql \#homebrew
