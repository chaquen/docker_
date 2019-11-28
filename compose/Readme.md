# Docker compose
Es una herramienta que permite ejecutar multiples contenedores.

## ¿Cómo lo instalo?
	
Acceda al [sitio web](https://docs.docker.com/compose/)

### Paso 1. Acceda como root.

	sudo su 

### Paso 2. Ejecute la siguiente linea de comando.

	sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

### Paso 3. Aplique permisos paar ejecutar el binario

	sudo chmod +x /usr/local/bin/docker-compose

### Paso 4. Verifique la instalación

	docker-compose

Esto le mostrara el listado de comando permitidos por esta herramienta.


# Crear docker compose

### Paso 1. Creamos un archivo .yml 

Para consultar la documentación de docker compose dirigase a este [sitio web](https://docs.docker.com/compose/)

	version: " version de docker compose" [version](https://docs.docker.com/compose/compose-file/compose-versioning/)
	services: "servicios (contenedores que vamos a definir)"
    volumes (opcional):
    networks (opcional):

#### Ejemplo 
	
	version: "3"
	services: 
    	web:
      		container_name: nginx
      		ports: 
          		- "8080:80"
      		image:  nginx  

### Paso 2. Crear los contenedores 
Debes estar en la raiz donde esta el documento .yml

	docker-compose up -d

### Paso 3. Comprobar 
	
	http://localhost:8080/

Ahora tenemos nuestro servidor nginx ejecutandose

### Extra. Eliminar

	docker-compose down	

# Variables de entorno.
 
Las variales de entorno son valores que deseamos definir para nuestros servicios, veamos un ejemplo con MYSQL.

#### Ejemplo 1. Definir las variables en el archivo .yml

	version: "3"
	services: 
    	db:
      		image: mysql:5.7
      		container_name: mysql
      		ports:
         		- "3307:3306"
      		environment:
        		- "MYSQL_ROOT_PASSWORD=12345678"
#### Ejemplo 2 Definir las variables en un archivo distinto .env
	
	version: "3"
	services: 
    	db:
      		image: mysql:5.7
      		container_name: mysql
      		ports:
         		- "3307:3306"
      		env_file: nombre_archivo.env
        
#### Comprobar 

	docker exec -ti nombre_contenedor bash	

Una vez dentro del contenedor validamos las variables ejecutando el comando
	
	env	

	
# Volumes en Docker compose

#### Ejemplo volumes nombrados
	
	version: "3"
	services: 
    webapp:
	      container_name: nombre_del_contenedor
	      ports: 
	          - "8888:80"
	      image: nginx
	      volumes: 
	        - "vol2:/usr/share/nginx/html"
	volumes:
	    vol2:

Se puede dar de baja pero el volumen sera persitente y editable para validar puede acceder a la carpeta de los volumenes 

Para acceder a la ruta de docker

	docker info | grep -i root

Para acceder a la carpeta de docker

	cd /var/lib/docker

Para acceder a la carpeta de lso volumes

	cd volumes

Para acceder como sudo
	
	sudo su

Una vez alli acceda a la carpeta  data edite los archivos que quiera se recomienda el index.html

	cd _data


#### Ejemplo volumes de host

version: "3"
services: 
    webapp:
      container_name: nombre_del_contenedor
      ports: 
          - "8081:80"
      image: nginx
      volumes: 
        - "ruta_que_quiera_compartir_con_docker:/usr/share/nginx/html"

#### Extra. ¿Cómo acceder a el contenedor?
En caso de que requieras acceder al contendor puedes hacerlo a través del comando 
	
	docker exec -ti nombre_del_contenedor bash



