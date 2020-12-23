FROM craigmiller160-nginx-base:1.0.0

RUN mkdir -p /var/www/cert
COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /var/www
COPY authcode.txt /var/www

ENTRYPOINT ["nginx","-g","daemon off;"]
