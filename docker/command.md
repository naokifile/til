# command

## docker pull
イメージの取得

```
docker pull ubuntu:latest
```

## docker build
イメージの作成

```
docker build -t naokifile/test .
```

```
-t          名前とタグの指定
--no-cache  イメージ作成時にキャッシュを使用しない
```

## docker run
イメージの起動

```
docker run --rm -it ubuntu:latest /bin/bash
```

```
-name       コンテナに名前をつける
--rm        コンテナ終了時に削除する
-d          バックグラウンドで起動する
-i          STDINを開きっぱなしに
-t          ttyを割り当て
```

## docker ps
実行中のコンテナ一覧を表示

```
docker ps
```

```
-a          実行中だけでなく全てのコンテナを表示
```