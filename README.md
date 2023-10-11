# statech-interview-backend
スタテクの選考を受けて合格するまでの物語

## ローカルでの起動方法

### Python環境のセットアップ
```shell
$ make setup
```
- 「Author」パートは"n"を入力してEnter。それ以外のパートは全てEnterのみ。

### API起動
```shell
$ make up
```
- APPコンテナとMySQLコンテナが立ち上がる<br>
- Uvicornが立ち上がるので、そこに表示されたURL（[http://0.0.0.0:8000](http://0.0.0.0:8000)）に/docsをつけるとSwaggerUI上でAPIの挙動を確認できる。
- リポジトリのコード全体をaiagent-apiコンテナ内のappにマウントしており、pythonインタープリタは[/app/.venv/bin/python]となる。

### コンテナ終了
```shell
$ make down
```

### 1からコンテナ立ち上げ
```shell
$ make build
```
- Docker環境に関わるコードを変更し、イメージのビルドから行う必要がある場合に使う

## その他重要コマンド

### フォーマッタ起動
```shell
$ make fmt
```

### リンタ起動
```shell
$ make lint
```

### テスト起動
```shell
$ make test
```

## 環境変数について
- 検証環境(AWS)が整うまで、.envファイルによってシークレットな環境変数を取り扱う。
  - 責任者から.envファイルを共有してもらい、/envに格納することでAPIが動く。

## その他注意点
- プルリクを出す前に、必ずリンタ・フォーマッタ・テストが通ることを確認する。