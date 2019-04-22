## mapd

### memo
- mapdのdockerファイルを取得
```
$ docker pull mapd/mapd-ce-cuda:latest
```
- docker実行  
※ ```-v /home/username/mapd-storage```は自身で使用するパスを指定
```
$ docker run \
    --runtime=nvidia \
    -d \
    --name mapd \
    -p 9090-9092:9090-9092 \
    -v /home/username/mapd-storage:/mapd-strage \
    mapd/mapd-ce-cuda
```
- webから実行コンテナにアクセス  
[http://localhost:9092](http://localhost:9092)




---
### link
- [mapd（docker file）](https://hub.docker.com/r/mapd/mapd-ce-cuda/)
- [mapd 使い方](https://qiita.com/nodokaodayaka/items/423390ffd1c0dd8f414e)
