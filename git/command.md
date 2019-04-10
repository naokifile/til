## git

### 新規作成関連
- gitを初期設定  
実行したディレクトリ直下にgitの各種設定ファイル等が作成される
```
$ git init
```

- リモートリポジトリからデータをgitディレクトリにコピーする   
→ リモートリポジトリのデータをコミットログ等を含め丸々コピー
```
$ git clone https://github.com/naokifile/xxxx.git
```

---
### 変更処理
- 変更内容をステージに追加する
```
$ git add dirname/filename/.
```

- 変更内容をコミットする
```
$ git commit
```