# Cambiar el nombre a Dockerfile 

  ###Aqui aprenderemos como se cambia el nombre al dockeerfile 


# Estructura de Dockerfile    


    FROM centos 
	RUN yum -y install httpd
	RUN echo "hola mundo :) desde MyDockerfile" > /var/www/html/index.html
	CMD apachectl -DFOREGROUND


 #Cambiando el nombre del Dockerfile   
  
    
  ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen -f MyNUevoNombre
      Dockerfile .


  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  



