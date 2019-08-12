# Uso de VOLUME en Dockerfile

Aqui veremos un ejemplo de como se usa en un Dockerfile la sentencia VOLUME

	FROM centos
	VOLUME /opt/
	USER root

Esta opción nos permitira mapear los datos creados en nuestro contenedor dentro de la carpeta /opt/ como lo indica la sentencia 

	VOLUME /opt/	

Esto creara una carpeta /var/lib/docker/volume 

### Validar la ruta del root de Docker

#### Crear imagen

		docker build -t  volumen_test .

#### Crear contenedor

		docker run -dti --name volumen_test volumen_test

#### Interactuar con el contenedor

		docker exec -ti volumen_test bash

Luego de ello accederemos a nuestro S.O del contenedor 

		cd opt/

Luego creamos los archivos
		
		touch file.txt

Salimos del S.O

	exit
  
### Ver los archivos en el docker host

	docker inspect volumen_test | grep -i vol

Copiamos la ruta de la propiedad Source, esta es la ruta de nuestro volumen.




