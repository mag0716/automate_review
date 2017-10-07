# automate_review
レビューを自動化するための調査

## やりたい事

* PR 発行契機で以下を実行し、PR にコメントする
  * ビルド
  * フォーマッター
  * Lint
    * error になったら FAILED
  * テスト
    * 1件でも失敗したら FAILED

## Danger なし

### 参考

* http://knowledge.sakura.ad.jp/knowledge/5293/

## Danger

### Danger の導入

* https://github.com/danger/danger

#### Android + Jenkins 用

* https://qiita.com/toshihirooya/items/2d2a3c28071892d909e5
* http://danger.systems/plugins/jenkins.html
* https://github.com/loadsmart/danger-android_lint

### 参考

* http://tech.connehito.com/entry/danger
* https://techblog.recruitjobs.net/development/danger_driven_development
* https://qiita.com/noboru_i/items/2f30296db1c8a6dfbd9b

#### サンプル

* https://github.com/loadsmart/danger-android_lint
