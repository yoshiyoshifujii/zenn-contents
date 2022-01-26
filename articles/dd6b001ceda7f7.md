---
title: "macosにbrewでインストールしたmysqlクライアントを使うときに忘れない"
emoji: "🖥"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["mysql", "mac"]
published: true
---
# ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

って出るのなんでーってなったときは、

```shell
brew services start mysql
```

すればいける。

# ERROR 1045 (28000): Access denied for user ...

って出るのなんでーってなったときは、 `localhost` って指定してるところを、 `127.0.0.1` とかにしたらいける。

```shell
mysql -u root -p -P 13306 -h 127.0.0.1
```
