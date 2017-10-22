# Nginx

---

# インストール

## CentOS

```
$ sugo yum install -y nginx
```

補足
- [CentOSにnginxをインストールする方法 \- Qiita](https://qiita.com/NaokiIshimura/items/08aac94a184d1a00d39b)

---

# コマンド

## 基本

```
$ sudo nginx
$ sudo nginx -s stop
$ sudo nginx -s reload
```

## サービス起動・停止

### CentOS 6

```
# 起動
$ sudo service nginx start

# 停止
$ sudo service nginx stop

# 再起動
$ sudo service nginx restart

# 設定ファイルの再読込
$ sudo service nginx reload
```

### CentOS 7

```
# 起動
$ sudo systemctl start nginx.service

# 停止
$ sudo systemctl stop nginx.service

# 再起動
$ sudo systemctl restart nginx.service

# 設定ファイルの再読込
$ sudo systemctl reload nginx.service

# 状態確認
$ sudo systemctl status nginx.service
```

## 自動起動

### CentOS 7

```
# 自動起動を設定
$ sudo systemctl enable nginx.service

# 自動起動を停止
$ sudo systemctl disable nginx.service
```

---

# コンフィグ

## nginx.conf

```
/etc/nginx/nginx.conf
```

---

# バーチャルホスト

## ディレクトリ

```
/etc/nginx/sites-available
/etc/nginx/sites-enabled
```

## コンフィグ

```
/etc/nginx/sites-available/my-app
```

## シンボリックリンク

```
ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
```

---

# リバースプロキシ

参考
- [How to proxy web apps using nginx?](https://gist.github.com/soheilhy/8b94347ff8336d971ad0)
- [nginx でリバースプロキシするときの Tips : あかぎメモ](http://blog.akagi.jp/archives/3883.html)

# Rails

参考
- [【Rails】WEB/APサーバ構成に応じたNginx設定 \- Qiita](https://qiita.com/NaokiIshimura/items/7cb2390243939a34754f#rails)

---

# sample

## sorry

sorryページで利用するコンフィグ

## reverse-proxy

リバースプロキシのサンプルコンフィグ

## rails-passenger

RailsアプリをPassengerと連携させるコンフィグ

参考
- [CentOSにnginxとpassengerを導入してRailsアプリと連携させる \- Qiita](https://qiita.com/NaokiIshimura/items/24e0b911ca411421205a)

## rails-sock

RailsアプリをUnixドメインソケットで連携させるコンフィグ

config/puma.rb

```
# UNIXドメインソケット
bind "unix://#{Rails.root}/tmp/sockets/puma.sock"
```

## rails-proxy

Railsアプリをリバースプロキシで連携させるコンフィグ

## rails-loadbalancing

Railsアプリをロードバランシングで連携させるコンフィグ
