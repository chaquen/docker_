# ¿Qué son los volumenes nombrados?

Son volumenes creados que podemos asignar a nuestros contenedores y que nos ayudaran a tener persistencia de datos.

# Crear un volumen.

	docker volume create  nombre_del_volumen 			

Los volumenes se almacenaran en la carpeta root de docker para consultarla puedes usar el comando 
	
	docker info | grep -i root

debes acceder como usuario root para ello puedes usar el comando 
	
	sudo su

# Crear el contenedor y asignarle un volumen

Para este ejemplo usaremos Mysql por lo que la ruta donde se almacenan los datos en el contenedor esta dada en "/var/lib/mysql/"
	
	docker run -d --name mysql -v nombre_de_volumen:/var/lib/mysql -p 3307:3306 -e "MYSQL_ROOT_PASSWORD=123456" -e "MYSQL_DATABASE=docker_db" mysql:5.7

Si eliminamos el contenedor el volumen seguira persistendo.
