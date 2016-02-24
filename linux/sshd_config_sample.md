# sshdの設定例

* 公開鍵を設置しておく
* `firewalld`か`iptables`が起動中な場合は反映前にSSHのポート番号を変更しておく

```
$ sudo vi /etc/ssh/sshd_config
+Port 10022                # ポートを22番以外にする
+Protocol 2                # SSHバージョン2を使う
+PermitRootLogin no        # ルートでのログインを禁止
+PubkeyAuthentication yes  # 公開鍵認証でのログインを許可
+PasswordAuthentication no # パスワードでのログインを禁止

# sshdを再起動して反映
$ systemctl restart sshd.service
```

**接続したまま新しい端末で接続テストしたほうが安心**
