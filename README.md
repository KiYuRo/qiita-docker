# Docker環境構築テンプレート
DockerでPython環境とDBを構築する際のテンプレート

# ディレクトリ構成
```
C:.
├─app           # pythonのコード
└─docker        # dockerで使用するファイル
    ├─app       # appコンテナの設定ファイル
    └─database  # databaseコンテナで使用するファイル
        ├─data  # databaseコンテナのデータを永続化するためのディレクトリ
        └─init  # コンテナ起動時に実行するSQLファイル
```


# コンテナ起動
dockerディレクトリに移動
```
cd docker
```

コンテナ起動
```
docker compose up -d
```


# appコンテナ
appコンテナ接続
```
docker compose exec app /bin/bash
```

python実行
```
python app.py
```


# databaseコンテナ
databaseコンテナ接続
```
docker compose exec database /bin/bash
```

データベース接続
```
psql -U root
```


# コンテナ削除
```
docker compose down
```
