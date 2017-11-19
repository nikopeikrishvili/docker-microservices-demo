FROM nginx
COPY conf/nginx/nginx.conf /etc/nginx/conf.d/sites.conf
COPY /code /usr/share/nginx/html/user
RUN apt-get update && apt-get install -y curl
RUN  apt-get install -y php-fpm php-mysql
RUN curl -sS https://getcomposer.org/installer |  php -- --install-dir=/usr/local/bin --filename=composer
RUN rm /etc/php/7.0/fpm/pool.d/*
COPY conf/php-fpm/www.conf /etc/php/7.0/fpm/pool.d/www.conf
RUN echo "exit 0" > /usr/sbin/policy-rc.d
CMD /etc/init.d/php7.0-fpm restart && nginx -g "daemon off;"
CMD service php7.0-fpm start
EXPOSE 80