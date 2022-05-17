FROM nginx:alpine

RUN adduser -S -G www-data www-data

ADD nginx.conf /etc/nginx/
ADD app.conf /etc/nginx/conf.d/default.conf
RUN echo "upstream app-upstream { server app:9000; }" > /etc/nginx/conf.d/upstream.conf

EXPOSE 80

CMD ["nginx"]