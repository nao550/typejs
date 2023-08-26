<https://qiita.com/tanakaPH/items/84aedaad8c0f5958a5f0>

# Node.js コンテナの起動

$ docker-compose run --rm app /bin/bash

# Expressアプリケーションの雛形作成

root@2e490c20618c:/app# npx express-generator

# 依存パッケージのインストール

root@2e490c20618c:/app# npm install

# nodemonをインストール

root@2e490c20618c:/app# npm install -D nodemon

npm install

package.json の修正
"scripts": {
  "dev": "nodemon ./bin/www",
  "start": "node ./bin/www"
},

docker-compose.yml

# 起動後に実行するコマンド

command: npm run dev

# localhost:3000 で Express が起動することを確認

# TypeScriptと型定義をインストール

root@2e490c20618c:/app# npm install -D typescript @types/express @types/cookie-parser @types/morgan @types/http-errors

# tsconfig作成

root@2e490c20618c:/app# npx tsc --init

tsconfig.json の書き換え
"allowJs": true,       /*Allow javascript files to be compiled.*/
"outDir": "./dist",    /*Redirect output structure to the directory.*/

bin/www ファイルの書き換え
/**

* Module dependencies.
 */
var app = require('../dist/app');
var debug = require('debug')('app:server');
var http = require('http');

コンパイルしてからnodemonを起動するようにします。
command: sh -c 'npx tsc; npm run dev'

# docker

docker build -t typejs .
docker run -p 8080:8080 -d typejs

docker exec -it <container id> /bin/sh

docker compose run --rm app /bin/bash  
