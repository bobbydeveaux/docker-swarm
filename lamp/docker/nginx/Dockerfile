FROM nginx:alpine

RUN apk update && apk upgrade && \
    apk add --update curl wget bash tree

ADD ./conf/default.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]