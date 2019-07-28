#imagen con el uso de comando ENV
FROM centos
RUN yum -y install httpd
ENV contenido <html><head><title>Prueba de ENV</title></head><body>Este es un ejemplo las variables de entorno ENV en un archivo dockerfile</body></html>
RUN echo "$contenido" > /var/www/html/index.html
CMD apachectl -DFOREGROUND
