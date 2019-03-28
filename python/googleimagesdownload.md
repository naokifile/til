# google images download
google画像検索から指定したキーワードで画像を自動的に取得するもの

## command
```
$ googleimagesdownload -k "keyword"
```

```
-k          検索のキーワード
-l          画像取得の上限数
-ri         大量の画像を取得するときのオプション？
-cd         chromedriverを使用するときのオプション
```

既定では上限が200?で、上限を解除するにはchromedriverが必要

---
## chromedriverを利用した画像取得
1. chromeのバージョンを確認
    - chromeを開き、「設定」から「chromeについて」を開く
1. バージョンに対応したchromedriverをダウンロードする
    - url: [http://chromedriver.chromium.org/downloads](http://chromedriver.chromium.org/downloads)
1. ダウンロードしたchromedriverを対象のディレクトリに保存
1. 以下のコマンドを実行
```
$ googleimagesdownload -k "keyword" -l limitSize -ri -cd /pathOfChromedriver
```
