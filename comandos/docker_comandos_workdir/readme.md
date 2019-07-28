# Indicar el direcorio de trabajo

  ### Aqui usamos el comando WORKDIR.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    

    
    FROM centos
    RUN yum -y install httpd
    WORKDIR /var/www/html
    COPY index.html  .
    CMD apachectl -DFOREGROUND

  Aqui podemos ver varios comandos usados con anterioridad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo WORKDIR.

    WORKDIR /var/www/html

  Este comando permite establecer una ruta que indica al comando COPY cual es el directorio actual.
  El punto (.) se utiliza para indicar que se copie en el directorio actual en este caso es /var/www/html, si se desea usar una   variable de entorno con una dirección /var/www en lugar del punto debe ir html

  ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  