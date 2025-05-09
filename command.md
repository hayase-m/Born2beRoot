### 再起動
```
sudo reboot
```

### 仮想マシンを終了
```
sudo shutdown -h now
```

### OSのバージョン確認
```
cat /etc/os-release
```
### ホスト名の確認
```
hostname
```

### ホスト名の変更
```
sudo hostnamectl set-hostname <評価者のログイン名>42
```

### ユーザー一覧表示
```
cat /etc/passwd
cut -d: -f1 /etc/passwd
getent passwd
```

### グループ一覧表示
```
getent group
```
### 特定のユーザーが所属するグループ確認
groups <ユーザー名>
id <ユーザー名>


### 新規ユーザー作成
```
sudo adduser <新ユーザー名>
```
### ユーザーのグループ追加
```
sudo usermod -aG <グループ名> <ユーザー名>
```

### ユーザー削除
```
sudo deluser <ユーザー名>
sudo deluser --remove-home <ユーザー名>
```

### グループ作成
```
sudo groupadd <新グループ名>
```

### グループ削除 (評価者が指示する場合、慎重に)
```
sudo groupdel <グループ名>
```

### パスワードポリシー設定ファイルの確認
```
cat /etc/pam.d/common-password
```

### ユーザーのパスワード有効期限情報確認
```
sudo chage -l <ユーザー名>
```

### パスワード変更
```
sudo passwd <ユーザー名>
```

### パーティション情報表示
```
lsblk
```



### SSHサービスの状態確認
```
sudo systemctl status ssh
sudo systemctl status sshd
```


### SSH設定ファイル確認
```
cat /etc/ssh/sshd_config

```

### SSHポートの表示
```
ss -tlpn | grep ssh
```
### UFWの状態確認
```
sudo ufw status
sudo ufw status verbose
sudo ufw status numbered
```

### UFWの設定
```
sudo ufw allow <ポート番号>
```

### UFWの削除
```
sudo ufw delete allow <ポート番号>
```

### sudoersファイルの内容確認
```
sudo visudo
```


### スクリプトの存在とパーミッション確認
```
ls -l /usr/local/bin/monitoring.sh
```

### スクリプトの実行テスト (手動で)
```
/usr/local/bin/monitoring.sh
```

### cronの設定確認 (10分ごとに実行されるか)
```
sudo crontab -l -u root
cat /etc/crontab
ls -l /etc/cron.d/
ls -l /etc/cron.hourly/ /etc/cron.daily/ /etc/cron.weekly/ /etc/cron.monthly/
```

### crontabを開く
```
sudo crontab -e
```
### cronの停止
```
sudo systemctl disable cron
```
