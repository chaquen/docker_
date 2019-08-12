# ¿Como limitar los recursos de un contenedor?

### Ejemplo de como administrar los recursos de un conteendor

Crear un contenedor, para este ejemplo usaremos una imagen de [Mongo](https://hub.docker.com/_/mongo) 

	   docker run -d --name nombre_contenedor mongo
 
 #### ver el uso de recursos de un contenedor

      docker stats nombre_contendor

 ####  Limitar la memoria

      docker run -d -m "1024mb" --name mongo3 mongo

	  docker run -d -m "1gb" --name mongo3 mongo	      
 
####  Limitar las cpus
	
	  docker run -d -m "1024mb" --cpuset-cpus 0-1  --name mongo3 mongo	 

Estos comando pueden ir juntos al ejeutar run


 




