FROM nginx:alpine

RUN apk update && apk upgrade && \
    apk add --update curl wget bash tree

ADD ./conf/default.conf /etc/nginx/conf.d/default.conf
ADD ./conf/fastcgi_params /etc/nginx/fastcgi_params
ADD ./index.php /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]