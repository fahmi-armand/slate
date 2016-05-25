# Kaskus Oauth 2 Micro Service

Kaskus Oauth 2 micro service is mini application to serve oauth 2 authorization.
It serves as Authorization Server for Kaskus Application

### Required Softwares
* php 5.6
* mongodb extension
* composer

### Installation

You need composer installed globally:

```sh
php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php
php -r "if (hash('SHA384', file_get_contents('composer-setup.php')) === '7228c001f88bee97506740ef0888240bd8a760b046ee16db8f4095c0d8d525f2367663f22a46b48d072c816e7fe19959') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
mv composer.phar /usr/local/bin/composer
```

```sh
git clone git@github.com/kaskus-api-oauth.git
cd kaskus-api-oauth
composer install
cp .env.example .env
nano .env
// edit .env file by setting up database path
php artisan migrate
php artisan db:seed
```

### Running

```sh
php artisan serve
```

### Development Guide

#### Building

* install ant
* run ant -buildfile others/build.xml or add `alias anto='ant -buildfile others/build.xml'` in ~/.bash_aliases

build normal
```
anto
```

build for running test only
```
anto tests
```

### Deployment Guide

#### Nginx

Use similar environment
```
server {
    listen 80;
    server_name oauth.kaskusplayground.local;
    root /home/kaskus/oauth.kaskusplayground.local/public;

    index index.html index.htm index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php$is_args$args;
    }

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    access_log /var/log/nginx/oauth.access.log;
    error_log  /var/log/nginx/oauth.error.log;

    sendfile off;

    client_max_body_size 100m;

    location ~ \.php$ {
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass 127.0.0.1:9001;
        fastcgi_index index.php;
        include /etc/nginx/conf/custom/api.conf;
        include fastcgi_params;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_intercept_errors off;
        fastcgi_buffer_size 16k;
        fastcgi_buffers 4 16k;
    }

    location ~ /\.ht {
        deny all;
    }
}
```