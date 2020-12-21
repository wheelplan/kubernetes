FROM nginx:stable-alpine
ADD  ngx.tar.gz /etc/nginx/
ADD  modsecurity.tar.gz /usr/local/
COPY nginx /usr/sbin/nginx
RUN  apk add --no-cache pcre-dev && mkdir -p /var/cache/nginx/client_temp
