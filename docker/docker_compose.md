# docker compose

アプリケーションに必要なコンテナをまとめて起動することができる  
（例： webサーバ・DBサーバを一緒に起動する）  
設定はymlファイルに記述する。

## インストール
1. githubから取得
    - ```$(uname -s)``` ： OS名を取得
    - ```$(uname -m)``` ： ハードウェアタイプを取得
```
$ sudo curl -L https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
```

2. 実行権限の付与
```
$ sudo chmod +x /usr/local/bin/docker-compose
```

3. インストールされているかの確認
```
$ docker-compose --version
```
---
## docker-compose.yml
- サンプル  
```
version: '3'
services:
  db:
    image: postgres
  web:
    build: .
    command: python3 manage.py runserver:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
    depends_on:
      - db
```
- version:  
　docker-composeで使用できるバージョンを定義
- services:  
ここにまとめて起動する対象のコンテナを定義する
    - この例では、dbとwebが対象のコンテナ
- image:  
docker hubからイメージを取得する
    - この例ではpostgresを利用する
- build:  
　Dockerfileのある場所
- command:  
　実行するコマンド
- volumes:
　bind mountするときのディレクトリを指定
    - この例では、カレントディレクトリをコンテナ内の/codeにマウントする
- ports:  
　ポートの指定
- depends_on:  
　起動するコンテナ間の依存関係を示す
    - ここでは、webが立ち上がる前にdbが立ち上がるようにする

---
## コマンド
- docker-composeの起動  
```
$ docker-compose up
```

- docker-composeの停止
```
$ docker-compose stop
```

- docker-composeの一覧表示
```
$ docker-compose ps
```

- 引数で指定したコンテナ内でコマンド実行
```
$ docker-compose run web rails s
```

