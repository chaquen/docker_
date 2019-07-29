# USUARIOS EN TU IMAGEN

  ###Aqui usamos el comando USER.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    


    FROM centos
    LABEL autor = "Creada por chaquen 2019-07-28"
    LABEL version = "Versión 1.0"
    LABEL sistema_oprativo = "Centos latest versión"
    LABEL servidor_web = "Apache latest versión"
    RUN yum -y install httpd
    RUN echo "$(whoami)" > /var/www/html/user1.html
    RUN useradd edgar
    USER edgar
    RUN echo "$(whoami)" > /tmp/user2.html
    USER root
    RUN cp  /tmp/user2.html /var/www/html/user2.html
    CMD apachectl -DFOREGROUND

     
  Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo USER.

      RUN useradd edgar
      USER edgar 

  Este comando permite agregar usuarios al contexto de ejecución de la imagen, durante la aejecución se deben tener en cuenta los permisos de cada uno de los usuarios, en este ejemplo vemos que agregamos el archivo creado con el usuario edgar, crea un archivo en la carpeta /tmp/user2.html, y luego se cambia el contexto de el usuario, para que este copie y agrege el archivo a la carpeta /var/www/html/user2.html


   ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  