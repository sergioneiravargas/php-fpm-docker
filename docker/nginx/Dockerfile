FROM nginx:alpine

RUN adduser -S -G www-data www-data

ADD nginx.conf /etc/nginx/
ADD app.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx"]
