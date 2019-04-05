# Dockerfile
作成したDockerfileを元に、コンテナを作成する。

## command
- ベースとするイメージを指定
```
FROM ubuntu
```

- Dockerfileの作成者を記述
```
MAINTAINER naokifile@test.com
```

- コンテナのビルド時にコンテナ内で実行される（docker build）
```
RUN apt-get install -y emacs
```

- 完成したイメージからコンテナを作成するときに実行する（docker run）
```
CMD python3 manage.py runserver 0.0.0.0:8888
```

- コンテナ内の指定したディレクトリをvolumeとして指定する
```
VOLUME /sample
```

- ファイルをコピーする
    - COPYとADDの違い
        - COPY:  
            リモートからファイルを追加できない
            圧縮ファイルが自動的に解凍されない
        - ADD:  
            リモートからファイルを追加できる
            圧縮ファイルが自動的に解凍される
```
COPY test.txt /sample
```
```
ADD https://github.com/github/test/master/README.md /sample
```

- 作業ディレクトリを指定する
```
WORKDIR /sample
```

- 環境変数の設定
```
ENV http_proxy http://xxx.co.jp:8080
```
