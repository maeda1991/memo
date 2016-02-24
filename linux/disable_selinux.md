# SELinuxを無効にする

```
# 現在の動作状況を確認
$ getenforce
Enforcing # 有効

# 一時的に無効にする
$ sudo setenforce 0
$ getenforce
Permissive # 無効

# 再起動後も無効にする
$ sudo vi /etc/sysconfig/selinux
-SELINUX=enforcing
+SELINUX=disabled
```
