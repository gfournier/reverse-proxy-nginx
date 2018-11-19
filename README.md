# nginx reverse proxy sample

How to install and configure nginx as a reverse proxy forwarding routes to different services.

## Install required packages

Install Flask
```
pip install flask
pip install tornado
```

Install nginx, Windows binaries can be found in releases. Just unzip.

## Start services

Start web apps (one per cmd instance):
```
python app1\wsgi.py
```

And:
```
python app2\wsgi.py
```

Start nginx.
More information to run on windows here: http://nginx.org/en/docs/windows.html
```
start nginx
```

## How to configure nginx for reverse proxy

More information can be found here: https://serverfault.com/questions/379675/nginx-reverse-proxy-url-rewrite

Configuration file is in `conf/nginx.conf`.
Merge these configuration lines into main nginx configuration file (`nginx/conf/nginx.conf`), inside the `server {...}` section.

Use the following command to reload nginx configuration:
```
nginx -s reload
```
