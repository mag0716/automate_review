# GitHub Actions

## [About GitHub Actions](https://help.github.com/en/articles/about-github-actions)

GitHub Actions は GitHub に組み込まれている CI サービス

### Core concepts

* Workflow
  * 1つ以上の Job から出来ていて、スケジューリングとイベントによる開始ができる
* Workflow run
  * 事前に設定された内容にしたがって実行され、Workflow ごとのログとステータスが確認できる
* Workflow file
  * YAML 形式で定義され、.github/workflows に保存される
* Job
  * Step で構成され、Job 毎に新しい仮想環境で実行される。並列での実行や前の Job に依存して直列で実行される
* Step
  * Job によって実行されるタスクで同じ仮想環境で実行される。コマンドや Action を実行する
* Action
  * Job を作成するために Step を組み合わせた個別のタスク
* Event
  * プッシュ、Issue、PR の作成など Action を実行するきっかけにできる
* Artifact
  * バイナリ、パッケージファイル、テスト結果、スクショ、ログなどで他の Job が使うこともできる

### Discovering actions in the GitHub community

https://github.com/actions から Action を探せる

### Usage limits

* リポジトリ毎に同時に20のworkflowを実行できる
* 1時間に1000API のリクエスト
* Job は6時間まで
* 同時に20のJobを実行できる

## [Configuring workflows](https://help.github.com/en/articles/configuring-workflows)

### [Configuring a workflow](https://help.github.com/en/articles/configuring-a-workflow)

* write, admin 権限であれば workflow の作成、変更ができる

#### Triggering a workflow with events

* `on` にトリガーイベントを指定する
* 定期的に実行する場合は `schedule` で指定する

#### Filtering for specific branches

* `branches` に対象となるブランチを指定することができる

#### Using the checkout action

* ビルドやテストする前にコードを取得するために `actions/checkout@v1` を利用する

#### Referencing actions in your workflow

* private リポジトリで定義された Action を利用するためには workflow ファイルと Action を
同じリポジトリに配置しておく必要がある
* public リポジトリで定義された Action へは `{owner}/{repo}@{ref}` or `{owner}/{repo}/{path}@{ref}` で参照できる
* 同じリポジトリの Action へは `{owner}/{repo}@{ref}` or `./path/to/dir` で参照できる

#### Adding a workflow status badge to your repository

* バッジで workflow のステタースを表示することができる

## [Managing a workflow run](https://help.github.com/en/articles/configuring-a-workflow)

workflow ごとのステータスや結果の確認、ペンディングされている workflow のキャンセル、失敗した workflow のデバッグ、ログの確認、成果物のダウンロードが可能

#### Viewing your workflow history

* Actions タブから確認できる
