# 注意点

1. タイムゾーン  
OSのタイムゾーン変更も忘れないで

2. FireWall  
firewalldの設定は自動化されていない。awsでやるならセキュリティグループの設定が必要になる。

3. Ansible  
そもそもAnsibleをインスコしなくては構築出来ませんね。
```
# yum -y install epel-release
# yum -y install ansible
```
展開場所は下記
```
/etc/ansible
ansible.cfg以外を上書きでコピーしたらいいと思います。
```
