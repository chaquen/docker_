# Volumenes compartidos entre contenedores

## Paso 1. Crear Dockerfile

	 FROM centos

	COPY start.sh /start.sh

	USER root

	RUN  chmod u+x /start.sh

	CMD /start.sh

## Paso 2. Crear carpeta comun
	
	Esta carpeta es la que compartiran nuestros contenedores	

## Paso 3. Crear script <<start.sh>>
El cual ejecuta el comando date 
	
	#!/bin/bash

	while true; do
		echo "<p>$(date +%H:%M:%S)</p>" >> /opt/index.html && \
		sleep 10
	done	

## Paso 4. Crear la imagen y los contenedores

### Construir la imagen 

	docker build -t nombre_de_la_imagen .

### Construir el contenedor que ejecuta el script

	docker run -v $PWD/comun:/opt -d --name nombre_contenedor nombre_de_la_imagen

### Construir el contenedor nginx 

En este contenedor se tendra compartido el resultado del script start.sh el cual ejecuta el comando date 
	
	docker run -d --name nombre_contenedor -v "$PWD/comun/:/usr/share/ngnix/html" -p 80:80 ngnix:alpine

## Paso 5. Acceder al servidor a través del navegador

	http://localhost:80/index.html	
