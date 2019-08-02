# CENTOS + APACHE + PHP + SSL

  ###Aqui construimos una imagen con centos + apache + php + ssl
 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    


    FROM centos:7 
	RUN \
		yum -y install \
		httpd \
		php \
		php-cli \
		php-common \
		mod_ssl \
		openssl
	RUN echo "<?php phpinfo();?>" > /var/www/html/index.php
	COPY ssl.conf  /etc/httpd/config.d/default.conf 
	COPY cuealquiernombre.crt   /docker_ssl.crt
	COPY cualquiernombre.key  /docker_ssl.key
	EXPOSE 443
	CMD apachectl -DFOREGROUND



  En este ejemplo podemos ver como se construye una imagen usando un certificado ssl de manera local 

  ## ¿Cómo crear mi certificado SSL?

   Ejecute el siguiente comando

        openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout cualquiernombre.key -out cualquiernombre.crt
	
   Aparecera una pantalla en la que deberá diligenciar los datos allí solitados.
       >> ... 
        Country Name (2 letter code) [AU]:

        State or Province Name (full name) [Some-State]:

        Locality Name (eg, city) []:

        Organization Name (eg, company) [Internet Widgits Pty Ltd]:

        Organizational Unit Name (eg, section) []:

        Common Name (e.g. server FQDN or YOUR name) []:localhost

        Email Address []:		

    
  ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  
