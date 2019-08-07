# Imagen Docker de Mongo

### Ejemplo de imagen Docker con [Mongo](https://hub.docker.com/_/mongo) 

Descargar imagen oficial de Mongo

	   docker pull mongo

Correr contenedor 

	   docker run -d --name nombre_contenedor -p 27017:27017 mongo

## Instalación de cliente para Mongo [ROBO 3T ROBOMONGO](https://robomongo.org) LINUX 
   Aqui podras encontrar el link original de instrucciones para [instalar](https://www.programsbuzz.com/index.php/article/install-robomongo-robo-3t-ubuntu-1804) RoboMongo.	

  ### Paso 1.
	Descargar [Robo Mongo](https://robomongo.org/download)

  ### Paso 2. Seleccionar la versión a instalar			
        Para este ejemplo Linux
  ### Paso 3. Crear directorio
        /usr/local/bin/robomongo
  ### Paso 4. Mueva los archivos descargados en el paso 1 a la carpeta anteriormente creada
	    sudo mv robo3t-1.2.1-linux-x86_64-3e50a65.tar.gz /usr/local/bin/robomongo
  ### Paso 5. Abra el directorio previamente creado y al que movimos los archivos descargados
	    cd /usr/local/bin/robomongo
  ### Paso 6. Descomprima el archivo 	  		 		
	    sudo tar -xvzf robo3t-1.2.1-linux-x86_64-3e50a65.tar.gz
  ### Paso 7. Ejecute el instalador
        ./robo3t 
  ### Paso 8. Acepte terminos y condiciones


##### Tip #####

Eliminar todos los contenedores.

		docker rm -fv $(docker ps -aq)




