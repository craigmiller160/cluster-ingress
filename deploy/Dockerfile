FROM nginx:1.15.10

RUN mkdir -p /var/www/cert
COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /var/www
COPY authcode.txt /var/www

ENTRYPOINT ["nginx","-g","daemon off;"]
