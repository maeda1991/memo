# firewalldの設定例

* sshdのポート番号も同時に変更する
* `--permanent`なしで一時的に反映、ありで再起動後も反映

```
# 現在のポートを確認
firewall-cmd --list-services
firewall-cmd --list-ports

# http(80)開放
firewall-cmd --add-service=http
firewall-cmd --permanent --add-service=http

# ssh用にtcpの10022番を開放
firewall-cmd --add-port=10022/tcp
firewall-cmd --permanent --add-port=10022/tcp

# ssh(80)閉鎖
firewall-cmd --remove-service=ssh
firewall-cmd --permanent --remove-service=ssh

# 反映されているか確認
firewall-cmd --list-services
firewall-cmd --list-ports
```

**接続したまま新しい端末で接続テストしたほうが安心**
