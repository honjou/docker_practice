<p align="center"><img src="https://raw.githubusercontent.com/honjou/docker_practice/images/logo.png"></p>

# Laravelローカル開発環境（Docker）

Docker（docker-compose）でLAMP環境（PHP/Apache/MySQL）を構築し、Laravelの新規プロジェクトをお手軽るに構築できます。

## 前提条件

お使いのPCにDockerをインストールしておいてください。

[「Docker for Windows」をインストール](https://laraweb.net/environment/6402/)

## 使い方

```
$ git clone https://github.com/honjou/doker_practice.git .
$ mkdir src
$ docker-compose build
$ docker-compose up -d

$ winpty docker-compose exec app bash

# composer create-project --prefer-dist laravel/laravel laraveltokyo "6.18.*"
# cd laraveltokyo
# chmod 777 -R storage/
# php artisan key:generate
```

詳細は[こちら](https://laraweb.net/environment/9034/)

### 注意

Laravelプロジェクト名を「laraveltokyo」以外にする場合はドキュメントルートも変更してください。

詳細は[こちら](https://laraweb.net/environment/8652/#3)

## ディレクトリ構造

```
DockerPractice
　┣ docker（docker本体）
　┣ src（laravel本体）← ※ここは管理対象外
　┣ .gitignore
　┣ docker-compose.yml
　┣ README.md
```

## コンテナ構成

```
　┣ app（laravelを動かすコンテナ）
　　　・Apache:2
　　　・PHP:7.4
　　　・Composer:2.0.9
     ・Node.js:12
　┣ db（MySQLを動かすコンテナ）
　　　・MySQL:5.7
　┣ phpmyadmin（phpMyAdminを動かすコンテナ）
　　　・PHPMyAdmin:5
　┣ mailcatcher（MailCatcherを動かすコンテナ）
```