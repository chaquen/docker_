FROM centos:7 
RUN \
	yum -y install \
	httpd \
	php \
	php-cli \
	php-common \
	mod_ssl \
	openssl


RUN echo "<?php phpinfo();?>" > /var/www/html/index.php

COPY ssl.conf  /etc/httpd/config.d/default.conf 
COPY cuealquiernombre.crt   /docker_ssl.crt
COPY cualquiernombre.key  /docker_ssl.key
EXPOSE 443
CMD apachectl -DFOREGROUND

