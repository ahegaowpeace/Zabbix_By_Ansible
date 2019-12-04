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
展開する場所は下記を参照。
```
/etc/ansible
※回答したらansible.cfg以外を上書きでコピーしたらいいと思います。
```
