# Nginx配置文件

> 一个Nginx代理多个vue项目的配置

##Vue项目配置

> vue-router设置

```javascript
let router = new Router({
    mode: 'history',
    base:'/kprm-web/',
    routes: [
        // your routes
    ]
})
```

> config/index.js 打包设置(设置build下的 assetsPublicPath)

```javascript
assetsPublicPath: '/kprm-web/'
```

##nginx.conf配置

```javascript

#user  nobody;
worker_processes  1;

#error_log  logs/error.log;
#error_log  logs/error.log  notice;
#error_log  logs/error.log  info;

#pid        logs/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       mime.types;
    default_type  application/octet-stream;

    #log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
    #                  '$status $body_bytes_sent "$http_referer" '
    #                  '"$http_user_agent" "$http_x_forwarded_for"';

    #access_log  logs/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    #keepalive_timeout  0;
    keepalive_timeout  65;

    #gzip  on;

    server {
        listen       8088;
        server_name  localhost;
        root /opt;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;

        location / {
            try_files $uri $uri/ /baas-web/index.html;
        }

        location /baas-web {
            try_files $uri $uri/ /baas-web/index.html;
        }

        location /kprm-web {
            try_files $uri $uri/ /kprm-web/index.html;
        }

        location /bcmp-web {
            try_files $uri $uri/ /bcmp-web/index.html;
        }

        #error_page  404              /404.html;

        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }

        # proxy the PHP scripts to Apache listening on 127.0.0.1:80
        #
        #location ~ \.php$ {
        #    proxy_pass   http://127.0.0.1;
        #}

        # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
        #
        #location ~ \.php$ {
        #    root           html;
        #    fastcgi_pass   127.0.0.1:9000;
        #    fastcgi_index  index.php;
        #    fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
        #    include        fastcgi_params;
        #}

        # deny access to .htaccess files, if Apache's document root
        # concurs with nginx's one
        #
        #location ~ /\.ht {
        #    deny  all;
        #}
    }
}

```
