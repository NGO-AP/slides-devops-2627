FROM nginx:1.22

RUN rm /etc/nginx/nginx.conf

COPY nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /var/www/static

COPY index.html style.css jquery.min.js /var/www/static/

EXPOSE 80
