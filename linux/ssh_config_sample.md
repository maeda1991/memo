# `~/.ssh/config`の設定例

```
$ vi ~/.ssh/config
+Host example                          # 設定名
+    HostName            example.com   # ホスト名
+    Port                10022         # ポート番号
+    User                hoge          # ユーザー名
+    IdentityFile        ~/.ssh/id_rsa # 秘密鍵
+    ServerAliveInterval 60            # keep alive
+    ForwardAgent        yes           # エージェントフォワード(yes|no)

# 接続テスト
$ ssh example

# ちなみにconfigを設定しないでオプションを使う場合
$ ssh example.com -p 10022 -l hoge -i ~/.ssh/id_rsa -o ServerAliveInterval=60 -A
```
