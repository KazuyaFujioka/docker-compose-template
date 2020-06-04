## docker + postgresql
postgresqlバージョン: 12

### 起動方法
postgres配下で以下のコマンドを実行
```
docker-compose up -d
```

### 接続確認
パスワードはdocker-compose.ymlに記載しているもの
```
psql -h 127.0.0.1 -p 5432 -U postgres
```

### 注意
psqlでアクセスした場合、タイムゾーンはAsia/Tokyoになる  
IntelliJ or DataGripでアクセスするとタイムゾーンがUTCになってしまう  
AdvancedのVM optionsに以下を設定してIntelliJ or DataGripを再起動することでタイムゾーンを切り替えることができる  
```
-Duser.timezone=Asia/Tokyo
```
