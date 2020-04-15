# エラー

```zsh
$ mysql.server start

ERROR! The server quit without updating PID file (/usr/local/var/mysql/username.local.pid).
```

PIDファイルが存在していなかった

# 解決法

```zsh
# 空のPIDファイルを作成
$ sudo touch br-MBA.local.pid

# 権限を付与
$ sudo shmod /usr/local/var/mysql
```

上記の方法で解決しない場合はMySQLを再インストール

```zsh
$ brew unistall mysql

$ brew install mysql
```

Homebrewで通らない場合は手動でMySQLを削除

```zsh
$ sudo rm -rf /usr/local/mysql
$ sudo rm -rf /Library/StartupItems/MYSQL
$ sudo rm -rf /Library/PreferencePanes/MySQL.prefPane
$ sudo rm -rf /Library/Receipts/mysql-.pkg
$ sudo rm -rf /usr/local/Cellar/mysql*
$ sudo rm -rf /usr/local/bin/mysql*
$ sudo rm -rf /usr/local/var/mysql*
$ sudo rm -rf /usr/local/etc/my.cnf
$ sudo rm -rf /usr/local/share/mysql*
$ sudo rm -rf /usr/local/opt/mysql*
```

パスを通す

```zsh
$ echo 'export PATH="/usr/local/opt/mysql@5.6/bin:$PATH"' >> ~/.zshrc
$ source ~/.zshrc
```
