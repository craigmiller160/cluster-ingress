FROM nginx:1.15.10

COPY certificate.pem /var/www/cert/certificat.pem
COPY key.pem /var/wwww/cert/key.pem
COPY nginx.conf /etc/nginx/nginx.conf

ENTRYPOINT ["nginx","-g","daemon off;"]
