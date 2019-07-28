# Variables de entorno

  ### Aqui usamos el comando ENV.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    

    FROM centos
    RUN yum -y install httpd
    ENV contenido <html><head><title>Prueba de ENV</title></head><body>Este es un ejemplo las variables de entorno ENV en un archivo dockerfile</body></html>
    RUN echo "$contenido" > /var/www/html/index.html
    CMD apachectl -DFOREGROUND

   Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo ENV.

    
    ENV contenido <html><head><title>Prueba de ENV</title></head><body>Este es un ejemplo las variables de entorno <b>ENV</b> en un archivo dockerfile</body></html>

  Este comando permite crear variable en el entorno de ejecución de la imagen, para este ejemplo se agrego contenido con una estructura HTML

  ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  