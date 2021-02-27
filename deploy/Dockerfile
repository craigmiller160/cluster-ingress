FROM craigmiller160.ddns.net:30004/nginx-base:1.1.0

RUN mkdir -p /var/www/cert
COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /var/www

ENTRYPOINT ["nginx","-g","daemon off;"]
