# postMessage の挙動検証

Chrome for iOS にて、サイト開発者の意図しない `postMessage` が送られてくる現象が起きるとのこと。
その検証用のためのリポジトリです。

see: https://stackoverflow.com/questions/54079756/internal-chromium-postmessage-event

## 検証結果

### 通常のブラウザ (期待される動作)

`postMessage` ボタンを押すと以下の alert が表示される

* `https://site1.tetsu.io`
* `"hoge"`

### Chrome for iOS

ページをロードしただけで以下の alert が表示される

* `https://site1.tetsu.io`
* `{ .. なんらかのデータ ... }`

`postMessage` ボタンを押すともちろん通常ブラウザと同様の挙動となる


=> Chrome for iOS ではサイト開発者の意図しない `postMessage` が、サイトの `origin` で送られている (おそらくブラウザ側が送っている)
