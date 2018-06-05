# Proxy

    # nginx.conf (apache类似)
    server {
        listen 80;
        server_name test.swoole.com;

        root /opt/php/www/test.swoole.com/public_html;
        index index.html index.htm;
    
        location / {
            # 如果$uri对应的文件存在,在Nginx返回文件,否则把请求交给Swoole处理
            try_files $uri @swoole;
        }
    
        location @swoole {
            proxy_pass http://127.0.0.1:8080;
            proxy_http_version 1.1;
            proxy_set_header Connection "keep-alive";
            # Swoole通过$req->header['x-real-ip']拿到该参数
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $remote_addr;
            proxy_set_header Host $host;
        }
    }