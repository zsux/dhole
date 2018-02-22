
## cors
> curl -i -X POST -H "Origin: http://127.0.0.1:8089" http://kd.pt.com/v1/auth/login

```
server {
    charset utf-8;
    client_max_body_size 128M;
    listen      80;
    server_name kd.pt.com;
    root        /Users/joseph/data/projects/kdlc/rcm/backend/web;
    index       index.html index.php;
    autoindex   on;

    set $cors '';
    location / {
        index  index.php index.htm index.html;  
        if ($http_origin ~ '^https?://(127.0.0.1:8089|www\.exp\.com)') {
            set $cors '1';
        }
        if ($request_method = 'OPTIONS') {
            set $cors '${cors}o';
        }
        if ($cors = '1o') {
            add_header 'Access-Control-Allow-Origin' '$http_origin';
            add_header 'Access-Control-Allow-Credentials' 'true';
            add_header 'Access-Control-Allow-Methods' 'GET, POST, PUT, DELETE, OPTIONS';
            add_header 'Access-Control-Allow-Headers' 'Accept,Authorization,Cache-Control,Content-Type,DNT,If-Modified-Since,Keep-Alive,Origin,User-Agent,X-Requested-With,token';
            add_header 'Access-Control-Max-Age' 1728000;
            #add_header 'Content-Type' 'text/plain charset=UTF-8';
            #add_header 'Content-Length' 0;
            return 204;
        }
        if (!-e $request_filename){
            rewrite ^/(.*) /index.php?r=$1 last;
        }
    }

    location ~ \.php$ {
       
        if ($cors = '1') {
            add_header 'Access-Control-Allow-Origin' "$http_origin";
            add_header 'Access-Control-Allow-Credentials' 'true';
        } 
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        include fastcgi_params;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        proxy_connect_timeout 7200s;
        proxy_send_timeout   7200s;
        fastcgi_connect_timeout 7200s;
        fastcgi_read_timeout 7200s;
        fastcgi_pass 127.0.0.1:9009;
    }
}
```
