## docker + mysql
mysqlバージョン: 8

### 起動方法
mysql配下で以下のコマンドを実行
```
docker-compose up -d
```

### 接続確認
パスワードはdocker-compose.ymlに記載しているもの
```
mysql -h 127.0.0.1 -u root -p
```
