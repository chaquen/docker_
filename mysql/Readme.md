# Imagen Docker de Mysql

### Ejemplo de imagen Docker con [Mysql](https://hub.docker.com/_/mysql) 

Descargar imagen oficial de Mysql

	   docker pull mysql

Correr contenedor 

	   docker run -d --name nombre_contenedor -p 3333:3306 -e MYSQL_ROOT_PASSWORD=abc1234. mysql

Acceder al servidor Mysql en tu maquina.

		mysql -u root -h 127.0.0.2 -p --port 3333

### ¿Cómo Obtener la dirección del servidor 127.0.0.1?
	
		docker inspect nombre_contenedor

##### Tip #####

Eliminar todos los contenedores.

		docker rm -fv $(docker ps -aq)




