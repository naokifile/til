# mount

dockerにおけるマウント機能はdocker外にあるデータをコンテナ内で利用できるようにすること

マウント方法は以下の3つ
- bind
- volume
- tmpfs


---
## bind
ユーザが使用しているファイルやディレクトリをマウントする。  

- コンテナにボリュームをマウントする
    - `$(pwd)`
        - カレントディレクトリを指す
```
$ docker run -td --name mount1 -v "$(pwd)"/source:/app nginx:latest
```

上記コマンドを叩いて、`ls`を押してみると、、、
```
[root@sample test]# ls
test.txt  source
```
のような形で、指定した名前でディレクトリが作成される。  
※ --mountオプション（`--mount type=bind,source="$(pwd)"/source`）の場合、マウント先のディレクトリ(この例だと`sourceディレクトリ`)がないときはエラーになる。


---
## volume
/var/lib/docker/volumes直下にディレクトリが作成される。  
コンテナ外から対象のディレクトリ内のファイルの操作は非推奨。

- コンテナにボリュームをマウントする
    - `-v vol1:/app:ro`
        - ボリューム(vol1）を指定のディレクトリ(/app)にマウントする
    - `:ro `
        - 読み取り専用として開く
```
$ docker run -itd --name mount1 -v vol1:/app:ro nginx:latest
```


---
## tmpfs
ホストのメモリ領域をディレクトリとしてマウント。  
コンテナを停止したりすると、データは消える。


