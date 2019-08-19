FROM centos
USER root
RUN yum -y install httpd vim
COPY desing_two /var/www/html
CMD apachectl -DFOREGROUND
