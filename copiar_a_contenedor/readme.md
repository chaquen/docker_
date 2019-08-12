#  ¿Cómo copiar archivos a un contenedor y viceversa?

### Crear imagen a partir de un archivo Dockerfile

		docker run -d -p 81:80 --name nombre_contenedor nombre_imagen


### Copiar al contenedor

	   docker cp index.html apache:/usr/local/apache2/htdocs/index.html


### Viceversa la version 19.03 tiene un bug con cp del contenedor a el equipo local

    
### Correr contenedor 

	   docker run  -ti -d --name nombre_contenedor nombre_imagen 

### Acceder a el contenedor

	   docker exec -ti -u usuario_con_el_que_quiere_acceder_al_contenedor nombre_contenedor bash


 




