# Construir una imagen copiando código a tu imagen

  ### Aqui usamos el comando ADD.

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    

     FROM centos
     RUN yum -y install httpd
     ADD desing_one /var/www/html 
     CMD apachectl -DFOREGROUND
     
  Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo ADD.

     ADD desing_one /var/www/html 

  Este comando permite copiar, descargar contenido de una carpeta o url a nuestra imagen, en este caso ## esing_one  ## el cuál se encuentra en la raiz del de la carpeta donde se va a crear la imagen.

  ## ¿Cómo ejecutar este ejemplo?
  	
  	Construir

      docker build -t nombre_de_la_imagen .

  	Ejecutar

      docker run -d --name nombre_del_contenedor - puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  