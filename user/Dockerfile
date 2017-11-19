FROM nginx
COPY conf/nginx.conf /etc/nginx/conf.d/sites.conf
COPY /code /usr/share/nginx/html/user
RUN apt-get update && apt-get install -y curl
RUN  apt-get install -y php-fpm php-mysql
RUN curl -sS https://getcomposer.org/installer |  php -- --install-dir=/usr/local/bin --filename=composer
RUN service php7.0-fpm start 
RUN service nginx restart
RUN chown nginx:nginx /var/run/php/php7.0-fpm.sock
RUN chmod 066 /var/run/php/php7.0-fpm.sock
EXPOSE 80