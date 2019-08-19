# Crear imagenes en base de contenedores

Si tenemos contenedores que deseamos convertir en imagenes podemos usar el comando
		
		docker commit nombre_del_contenedor nombre_de_la_nueva_imagen

La cual creara una imagen con la configuración especificada en el contenedor

## ¿Cómo crear una imagen en base a un contenedor?

Primero debemos crear nuestro contenedor, en este caso vamos a crear un archivo Dockerfile

		FROM centos
		USER root
		RUN yum -y install httpd vim
		COPY desing_two /var/www/html
		CMD apachectl -DFOREGROUND

# Crear una imagen 

	docker build -t nombre_de_la_imagen .

# Crear un contenedor
	
	docker run -d --name nombre_del_contenedor -p 81:80 nombre_de_la_imagen 

# Acceder al contenedor

    docker exec -ti nombre_del_contenedor

   El archivo Dockerfile tiene instalado el editor de texto (vim)[https://www.vim.org/], el cual usaremos para editar los archivos necesarios en neustro contenedor

# Crear un archivo con vim
  
    vim prueba.html

Edite y agrege lo necesario en el archivo, para guardar el archivo use

	la tecla ESC + :wq 	

Salga del contenedor
		
	exit 
	
# ¿Cómo creamos nuestra imagen en base a nuestroo contenedor personalizado?	

Use el comando commit 

	docker commit nombre_del_contenedor nombre_de_la_nueva_imagen	


