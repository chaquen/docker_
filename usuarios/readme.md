# Imagen Docker para probar usuarios

### Ejemplo de imagen Docker para probar usuarios

Crear imagen a partir de un archivo Dockerfile

	   FROM centos
	   ENV prueba 1234
       RUN useradd chaquen
       USER chaquen

### Contruir el contenedor

	   docker build -t nombre_imagen .
	

### Correr contenedor 

	   docker run  -ti -d --name nombre_contenedor nombre_imagen 

### Acceder a el contenedor

	   docker exec -ti -u usuario_con_el_que_quiere_acceder_al_contenedor nombre_contenedor bash
 




