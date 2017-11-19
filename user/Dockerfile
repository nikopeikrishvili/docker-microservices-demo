FROM nginx
COPY conf/nginx.conf /etc/nginx/conf.d/sites.conf
COPY /code /usr/share/nginx/html/user
RUN apt-get update && apt-get install -y curl
RUN  apt-get install -y php-fpm php-mysql
RUN curl -sS https://getcomposer.org/installer |  php -- --install-dir=/usr/local/bin --filename=composer
RUN rm /etc/php/7.0/fpm/pool.d/*
COPY ./../common-conf/php-fpm/www.conf /etc/php/7.0/fpm/pool.d/www.conf
RUN service php7.0-fpm start 
RUN service nginx restart
EXPOSE 80