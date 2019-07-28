# Variables de entorno

  ### Aqui usamos el comando EXPOSE.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    
    
    FROM centos
    RUN yum -y install httpd
    COPY index.html /var/www/html
    # EXPOSE 
    #se comenta, pendiente explicación en el cursso de udemy :P
    CMD apachectl -DFOREGROUND

  Aqui podemos ver varios comandos usados con anterioridad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo EXPOSE.

    EXPOSE 

  Este comando permite establecer un nuevo puerto, sin embargo se debe configurar previamente el servidor para que responda al puerto expuesto.

  ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  