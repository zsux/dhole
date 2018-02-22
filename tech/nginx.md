#nginx proxy
  
  ssh dev 
  docker exec -it nginxproxy_web_1 bash
  cd /etc/nginx/conf.d
  vim proxy.conf

  server {
      listen 80;
      server_name rcm.dev.kdqugou.com;

      location / {
          proxy_pass http://10.30.42.249:8180;
          proxy_redirect off;
          proxy_set_header Host $host;
          proxy_set_header X-Real-IP $remote_addr;
          proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
          proxy_set_header X-Forwarded-Proto $scheme;
      }
  }
