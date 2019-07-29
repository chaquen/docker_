#imagen con el uso de comando LABEL
FROM centos
LABEL autor = "Creada por chaquen 2019-07-28"

LABEL version = "Versión 1.0"

LABEL sistema_oprativo = "Centos latest versión "

LABEL servidor_web = "Apache latest versión "

RUN yum -y install httpd

ENV contenido <html><head><title>Prueba de LABEL</title></head><body>Este es un ejemplo de el uso del comando LABEL, el cuál permite agregar metadatos descriptivos de la imagen</body></html>

RUN echo "$contenido" > /var/www/html/index.html

CMD apachectl -DFOREGROUND
