# Construir una imagen copiando código a tu imagen

  ###Aqui usamos el comando COPY.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    

     FROM centos
     RUN yum -y install httpd
     COPY desing_two /var/www/html 
     CMD apachectl -DFOREGROUND
     
  Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo COPY.

     COPY desing_two /var/www/html 

  Este comando permite copiar a nuestra imagen el contenido de una carpeta en especifico, en este caso ## desing_two  ## el cuál se encuentra en la raiz del de la carpeta donde se va a crear la imagen.


   ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor - puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  