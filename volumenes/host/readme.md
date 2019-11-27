# Volumenes de host
Estos son los datos que persisten en nuestro docker host, dentro de una carpeta del file system del anfitrion.

# Volumenes Named Volumes
Son similares a los volumenes Anonymus pero estos su tienen una carpeta nombrada por nosotros.


## Ejemplo de volumenes Host

### Crear el contenedor

		docker run -d -p 3307:3306 --name nombre_de_contenedor -e "MYSQL_ROOT_PASSWORD=12345678" -e "MYSQL_DATABASE=docker_db" -e "MYSQL_USER=docker_user" -e "MYSQL_PASSWORD=12345678" mysql

## Hacer backup  de una base de datos

		mysqldump -u root -h 172.17.0.2 -p12345678 sys > dump.sql

Ahora tendremos un archivo de respaldo de la base de datos sys

## Copiar el backup a la base de datos docker_db

		mysql -u root -h 172.17.0.2 -p docker_db < dump.sql

Con esto tendremos una base de datos inicializada, sin embargo si eliminamos  el contenedor y volvemos al recrearlo los datos copiados se perderan para evitar esto, pondremos en uso los volumenes	

## Eliminar el contenedor
	
	docker rm -f nombre_de_contenedor


# Ahora si veamonos como funcionan los volumenes 

### Primero buscar donde se guarda la información de MYSQL
#### 1 - Para MYSQL es el directorio /var/lib/mysql

#### 2 - Creamos una carpeta en /opt/ llamada mysql 

#### 3 - Creamos el contenedor y le mapeamos la ruta de nuestro volumen /opt/mysql

	docker run -d --name nombre_del_contenedor -p 3307:3306 -e "MYSQL_ROOT_PASSWORD=12345678" -v /opt/mysql/:/var/lib/mysql mysql
	
Ahora podemos ingresar a nuestra base de datos crear y manipular los datos y cada vez que recreemos el contenedor tendremos nuestra información salvagauardada.


### TIP 

#### ¿Cómo obtener la ip del conetendor ?

	docker inspect nombre_del_contenedor 

Busca la opción IPAddress dentro del resultado generado.	

