#imagen con el uso de comando EXPOSE
FROM centos
RUN yum -y install httpd
COPY index.html /var/www/html
# EXPOSE 
#se comenta, pendiente explicación en el cursso de udemy :P
CMD apachectl -DFOREGROUND