# ベースイメージとしてNginxを使用
FROM nginx:alpine

ENV NGINX_PORT=80

# Nginxの設定ファイルをコピー
RUN rm -f /etc/nginx/conf.d/default.conf
# COPY default.conf /etc/nginx/conf.d/default.conf
# COPY ./nginx.development.conf /etc/nginx/conf.d

# ポート80を公開
EXPOSE 80
