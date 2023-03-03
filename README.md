# docker-nginx

<pre>
<code>
# curl -fsSL https://get.docker.com/ | sudo sh

# sudo curl -L https://github.com/docker/compose/releases/download/1.25.1-rc1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
# chmod +x /usr/local/bin/docker-compose

# docker-compose up -d

# docker exec -it 이름 bash

# ufw allow from 원격지아이피 to any port 80 proto tcp
</code>
</pre>

# nginx 설치

<pre>
<code>
# apt update
# apt install nginx
# systemctl enable nginx
# systemctl start nginx
# systemctl status nginx

# pm2 server --spa docs 3000
# serve -p 3000 -s docs

ln -s dexense.conf /etc/nginx/sites-enabled/dexense.conf

apidoc -i ./examples -f .route.js -o ../docs -t ./template
</code>
</pre>

<pre>
<code>
server {
    listen 80;
    server_name developers.dexense.com


    location / {
        root   /home/user/myapp/build;
        index  index.html index.htm;
        try_files $uri $uri/ /index.html;
    }
    
    location /api {
        proxy_pass http://[서버 url];
    }
}
</code>
</pre>
