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

localhost にアクセスし、権限がないと言われたら

```docker-compose exec app bash```

```chown www-data storage/ -R```


# Vue.js導入
Laravel8.xではlaravel-mix6がデフォルトでインストールされている

Vue.js3とTypeScriptのインストールを行う

```
docker-compose run app npm install vue@next -D
docker-compose run app npm install vue-loader@next -D
docker-compose run app npm install @vue/compiler-sfc -D
docker-compose run app npm install @types/webpack-env typescript ts-loader -D
```
