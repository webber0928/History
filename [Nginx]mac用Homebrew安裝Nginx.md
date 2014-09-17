#Mac用Homebrew 安裝 Nginx
---

###在brew上安裝

用 `brew` 安裝 `nginx` 的指令：

```bash
$ brew install nginx
```

```
==> Installing dependencies for nginx: pcre, openssl
==> Installing nginx dependency: pcre
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/pcre-8.35.mavericks.bottle.tar.gz
######################################################################## 100.0%
==> Pouring pcre-8.35.mavericks.bottle.tar.gz
🍺  /usr/local/Cellar/pcre/8.35: 146 files, 5.8M
==> Installing nginx dependency: openssl
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/openssl-1.0.1g.mavericks.bottle.tar.gz
######################################################################## 100.0%
==> Pouring openssl-1.0.1g.mavericks.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the system
keychain. To add additional certificates, place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

This formula is keg-only, so it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

The OpenSSL provided by OS X is too old for some software.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/openssl/lib
    CPPFLAGS: -I/usr/local/opt/openssl/include

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.1g: 429 files, 15M
==> Installing nginx
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/nginx-1.6.0_1.mavericks.bottle.tar.gz
######################################################################## 100.0%
==> Pouring nginx-1.6.0_1.mavericks.bottle.tar.gz
==> Caveats
Docroot is: /usr/local/var/www

The default port has been set in /usr/local/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

To have launchd start nginx at login:
    ln -sfv /usr/local/opt/nginx/*.plist ~/Library/LaunchAgents
Then to load nginx now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.nginx.plist
Or, if you don't want/need launchctl, you can just run:
    nginx
==> Summary
🍺  /usr/local/Cellar/nginx/1.6.0_1: 7 files, 912K
```

###安裝後執行：

```bash
$ sudo nginx
```

###測試：

請開啓此URL：

```bash
http://localhost:8080
```
---

###Configuration

`nginx.conf` 的位置在：

```bash
/usr/local/etc/nginx/nginx.conf
```

###更改默認的 port

Nginx 默認的 port 為 `8080`, 將它更改成 `80`, 必須先停止運行中的 Nginx server：

```bash
$ sudo nginx -s stop
```

接著打開 `nginx.conf` ：

```bash
$ vim /usr/local/etc/nginx/nginx.conf
```

接著改變他:

```
server {
    listen       8080;
    server_name  localhost;

    #access_log  logs/host.access.log  main;

    location / {
        root   html;
        index  index.html index.htm;
    }
```

改成

```
server {
    listen       80;
    server_name  localhost;

    #access_log  logs/host.access.log  main;

    location / {
        root   html;
        index  index.html index.htm;
    }
```

儲存並啟動 Nginx：

```
$ sudo nginx
```

**ps.更改位置**

將html的位置移到使用者為webber的資料夾www裏面

```
server {
    listen       80;
    server_name  localhost;

    #access_log  logs/host.access.log  main;

    location / {
        root   /Users/webber/www;
        index  index.html index.htm;
    }
```
---

##參考連結

[Learn-a-holic Geek Notes](http://learnaholic.me/2012/10/10/installing-nginx-in-mac-os-x-mountain-lion/)
