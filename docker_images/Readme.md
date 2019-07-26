# ¿Qué es un dockerfile?

  Es el archivo que permite definir nuestras imagenes estas siempre se deben crear en base a un sistema operativo y deben tener un servicio que mantenga vivo o en ejución dicha imagen para ello se debe ejecutar un proceso en primer plano para que este mantenja en ejecución la imagen.

# ¿Cómo crear un dockerfile?
	
   El dockerfile es una archivo sin extención que sedebe llamr por convensión Dockerfile sin embago se puede tener diferentes nombres

# Lista de comando basicos de un Dockerfile
   
   Comando que inicia la imagen en base a un s.o (sistema operativo).
   
    FROM s.o
   
   Comando que instala los programas, librerias necesarios para la imagen
    
    RUN sentencia de instalación de acuerdo al s.o 

   Comando para ejecutar una comando que levante un servicio en primer plano ejemplo el servidor de apache 
    
    CMD  sentencia de ejecución en primer plano de acuerdo al s.o
# Lista de comandos para crear, ejecutar y realizar otras tareas con las imagenes y contenedores.
   
   Comando para construir la imagen 	
   
    docker build -d apache-centos:apache-cmd .

   ##### -d : para enviarlo al final 
   
   ##### apache-centos nombre de la imagen 
   
   ##### :apache-cmd label de la imagen para ayudar a identificar la imagen creada
   
   Tenga en cuenta que aqui no esta exponiendo los puertos para acceder al servicio de su contenedor 
  
  ## Ejemplo exponiendo un puerto

    docker run -d --name apache81 -p 81:80  apache-centos:apache-cmd 
    
   ##### --name apache81 : nombre de la imagen
    
   ##### -p 80:81 : puertos el PuertoDelContenedor:PuertoEquipoFisico
    
   ##### apache-centos:apache-cmd : nombre de la imagen base de un contenedor 

  ## Ver el listado de contedores 
   
   Lista  todos los contenedores

    docker ps -a 

   Lista los contenedores vivos 

    docker ps      	  
   
  ## Eliminar una imagen
   
   Comando para eliminar una imagen

    docker rm -fv apache81
  
  ## Historial de una imagen
   
   Comando para ver el histial de una imagen 

	docker history -H apache-centos:apache-cmd --no-trunc
   
   ##### -H : Para que muestre el historico en formato humano
   
   ##### apache-centos:apache-cmd nombre_de_la:imagen:label_de_la_imagen 
  
   ##### --no-trunc (opcional) : muestra el listado de cambios y comando agregado