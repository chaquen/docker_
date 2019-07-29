#imagen con el uso de comando USER
FROM centos
LABEL autor = "Creada por chaquen 2019-07-28"

LABEL version = "Versión 1.0"

LABEL sistema_oprativo = "Centos latest versión "

LABEL servidor_web = "Apache latest versión "

RUN yum -y install httpd

RUN echo "$(whoami)" > /var/www/html/user1.html

RUN useradd edgar

USER edgar

RUN echo "$(whoami)" > /tmp/user2.html

USER root

RUN cp  /tmp/user2.html /var/www/html/user2.html

CMD apachectl -DFOREGROUND
