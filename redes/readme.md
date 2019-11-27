# Red Bridge, la red por defecto de docker
Cada vez que se crea un contenedor se agrega a esta red <<Bridge>>, por defecto

## Comando para listar las redes	
	 
	docker network ls

## Comando para ver información de la red Bridge

	docker inspect bridge

#Crear una red y una subred 

Comando para crear una red

	docker network create nombre_de_la_red

Comando para crear una subred 172.124.10.0/24 y 172.124.10.1 pueden ser definidas por el usuario de pendiendo de la necesidad de la red

	docker network create -d bridge --subnet 172.124.10.0/24 --gateway 172.124.10.1 nombre_sub_red

## Conectar contenedor a una red.

### Paso 1. Crear red 
	
	 docker network create nombre_de_la_red


### Paso 2. Crar contenedores y agregarlos a la red 
 
	 docker run --network nombre_de_la_red -dti --name nombre_contenedor1 centos


	 docker run --network nombre_de_la_red -dti --name nombre_contenedor2 centos	


### Paso 3. Comprobar que se comunican 

	 docker exec nombre_contenedor bash -c  "ping test1"


### Extra. conectar un contenedor a otra red	 

	docker network connect la_red_a_la_que_me_quiero_conectar nombre_del_contenedor_que_quiero_conectar_a_la_nueva_red

# Existen otros tipos de red

## Red Host
La cual usara el mismo rango de red que usa el equipo anfitrion
	
		docker run --network host -dti --name nombre_contenedor1 centos

## Red None
La cual excluye el contenedor de cualquier tipo de red.

		docker run --network none -dti --name nombre_contenedor1 centos

