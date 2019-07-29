# Persistencia de datos en tu imagen

  ###Aqui usamos el comando VOLUME. (Pendiente avance en curso)

 Lo primero que debes hacer es construir tu archivo Dockerfile 


# Estructura de Dockerfile    

     
     
  
  Aqui podemos ver varios comandos usados con anterioidad, como lo son FROM, RUN, CMD, ahora veamos uno nuevo COPY.

     VOLUME /var/www/html 

  Este comando permite mantener la persistencia de datos luego de la desaparición de el contenedor.


   ## ¿Cómo ejecutar este ejemplo?
  	
  ### Construir

      docker build -t nombre_de_la_imagen .

  ### Ejecutar

      docker run -d --name nombre_del_contenedor -p puerto_que_vas_a_exponer:puerto_del_servidor_de_tu_imagen nombre_de_la_imagen  