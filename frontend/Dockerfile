FROM nginx

COPY html/ /usr/share/nginx/html

RUN mkdir /etc/nginx/templates

ENV API_URL=http://app:5000

COPY default.conf.template /etc/nginx/templates/