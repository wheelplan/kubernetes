FROM nginx:stable-alpine
ADD  ngx.tar.gz /etc/nginx/
ADD  modsecurity.tar.gz /usr/local/
COPY nginx /usr/sbin/nginx
COPY es-proxy.conf /etc/nginx/conf.d/
ADD  hexo.tar.gz /usr/share/nginx/html/
RUN  apk add --no-cache pcre-dev && mkdir -p /var/cache/nginx/client_temp
