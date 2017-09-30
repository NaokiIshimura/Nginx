# Nginx

---

# インストール

## CentOS

```
$ sugo yum install -y nginx
```

補足：[CentOSにnginxをインストールする方法 \- Qiita](https://qiita.com/NaokiIshimura/items/08aac94a184d1a00d39b)

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

# 設定ファイル

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

## 設定ファイル

```
/etc/nginx/sites-available/my-app
```

## シンボリックリンク

```
ln -s /etc/nginx/sites-available/my-app /etc/nginx/sites-enabled/my-app
```
