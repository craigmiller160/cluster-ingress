FROM nginx:1.15.10

RUN mkdir -p /var/www/cert
COPY certificate.pem /var/www/cert/certificate.pem
COPY key.pem /var/www/cert/key.pem
COPY nginx.conf /etc/nginx/nginx.conf
COPY index.html /var/www
COPY authcode.txt /var/www

ENTRYPOINT ["nginx","-g","daemon off;"]
