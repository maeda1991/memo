# 鍵のパスワードを毎回入力したくない

`ssh-agent`へ鍵とパスワードを登録すれば以降はパスワード入力しなくてOK

```
# ssh-agentを起動
$ eval `ssh-agent`

# 鍵を登録(パスワード入力を求められる)
$ ssh-add ~/.ssh/id_rsa
Enter passphrase for /home/hoge/.ssh/id_rsa:

# .bash_profileなどに書いておくと便利かも
$ vi ~/.bash_profile
+eval `ssh-agent`
+ssh-add ~/.ssh/id_rsa
```
