FROM nginx
COPY conf/nginx.conf /etc/nginx/nginx.conf
COPY /code /usr/share/nginx/html/user
RUN apt-get update && apt-get install -y curl
RUN  apt-get install -y php-fpm php-mysql
RUN curl -sS https://getcomposer.org/installer |  php -- --install-dir=/usr/local/bin --filename=composer
EXPOSE 80