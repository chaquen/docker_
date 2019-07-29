# METADATOS EN TU IMAGEN

  ###Aqui usamos el comando LABEL.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    


    FROM centos
    LABEL autor = "Creada por chaquen 2019-07-28"
    LABEL version = "Versión 1.0"
    LABEL sistema_oprativo = "Centos latest versión "
    LABEL servidor_web = "Apache latest versión "
    RUN yum -y install httpd
    ENV contenido <html><head><title>Prueba de LABEL</title></head><body>Este es un ejemplo de el uso del comando LABEL, el cuál permite agregar metadatos descriptivos de la imagen</body></html>
    RUN echo "$contenido" > /var/www/html/index.html
    CMD apachectl -DFOREGROUND


     
  Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo LABEL.

    LABEL autor = "Creada por chaquen 2019-07-28"
    LABEL version = "Versión 1.0"
    LABEL sistema_oprativo = "Centos latest versión "
    LABEL servidor_web = "Apache latest versión "

  Este comando permite agregar metadatos, lo cuál permite agregar datos descriptivos de la imagen.


   ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  