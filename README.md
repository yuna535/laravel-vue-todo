# laravel-vue-todo

## mysqlコンテナ作成
バージョン確認

```docker-compose up --build -d```

```docker compose exec db mysql -V```

## php nginx コンテナ作成

```docker compose exec web nginx -v```

* webコンテナの動作確認
* HTMLとPHPが表示されるか

```mkdir src/public```

```echo "Hello World" > src/public/index.html```

```echo "<?php phpinfo();" > src/public/phpinfo.php```

http://127.0.0.1:80/index.html 「Hello World」が表示されたらwebサーバーが正しく動作している。

http://127.0.0.1:80/phpinfo.php phpinfoの情報が表示されることを確認する。 webサーバーがappサーバーへphpを実行させ結果を返してくれることを確認。

確認が終わったらファイルは削除


## Laravelインストール
```docker-compose run app composer create-project --prefer-dist "laravel/laravel=8.*" .```