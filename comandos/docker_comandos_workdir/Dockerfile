#imagen con el uso de comando WORKDIR
FROM centos
RUN yum -y install httpd
WORKDIR /var/www/html
COPY index.html  .
# el punto se utiliza para indicar que se copie en el directorio actual en este caso es /var/www/html, si se desea usar una variable de entorno con una dirección /var/www en lugar del punto debe ir html
CMD apachectl -DFOREGROUND