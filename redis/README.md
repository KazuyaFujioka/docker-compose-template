## docker + redis
redisバージョン: 6

### 起動方法
redis配下で以下のコマンドを実行
```
docker-compose up -d
```

### 接続確認
redisのプロセス名を確認
```
docker-compose ps
```

docker shコマンド実行
```
docker exec -it [redisのプロセス名] sh
redis-cli
127.0.0.1:6379> 
```
と表示されればredisに接続できている
