# Zabbix-sever

1. タイムゾーン  
OSのタイムゾーン変更も忘れないで

2. FireWall  
firewalldの設定は自動化されていない。awsでやるならセキュリティグループの設定が必要になる。  

- 10050/tcp
- 10051/tcp

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
# Zabbix-agent

1. 権限  
rootユーザにならずにbecomeディレクティブの値をyesにするとsudoが実行できるようになる。

2. 鍵  
ssh用の鍵を以下の場所に格納する。
```
.ssh/private.pem
格納ディレクトリ:700
鍵ファイル:600
```

3. zabbix_agentd.conf
zabbixサーバのアドレス/zabbixエージェントのアドレス(ホスト名)をデフォルト設定から変更する必要がある。  
環境に合わせて下記ファイルを編集する。
```
roles/zabbix-agent/files/zabbix_agentd.conf
```
同じくインベントリのアドレスも

# 要件定義
インベントリでアドレスを設定するだけでzabbix監視環境を構築したい。  
アカパスは別途ファイルで管理したい。
