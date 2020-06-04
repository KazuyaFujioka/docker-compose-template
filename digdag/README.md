## docker + digdag
digdagバージョン: 0.9.36

### 起動前に作成(初回のみ)
digdagにはpostgresqlが必要なので、postgresqlを事前に起動させておくこと  
postgresqlのdocker-composeは[ここ](../postgresql)にある
```
psql -h 127.0.0.1 -p 5432 -U postgres
Password for user postgres:

-- digdagロール作成
CREATE ROLE digdag WITH PASSWORD 'digdag' NOSUPERUSER NOCREATEDB NOCREATEROLE LOGIN;

-- digdagデータベース作成
CREATE DATABASE digdag WITH OWNER digdag;

-- digdagデータベースに切り替え
\c digdag;

-- uuid-ossp拡張機能を有効化
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```

### 起動方法
digdag配下で以下のコマンドを実行
```
docker-compose up -d
```

### digdag Consoleへのアクセス
```
http://localhost:65432/
```

### WorkflowとProjectを作成して実行できるか確認(任意)

test.dig
```
timezone: Asia/Tokyo

+step1:
  echo>: Hello World!!

+step2:
  echo>: Fin.
```
