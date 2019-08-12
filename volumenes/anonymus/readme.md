# Volumenes Anonymus (NO ES BUENA PRACTICA)
Son los volumenes manejados por Docker generando una carpeta random, sin un nombre en especifico.

Al igual que los volumenes de host eprmiten almacenar información persistentemente pero con la unica diferencia de que nosotros no le damos al ruta donde queremos almacenar los datos del contenedor.

## ¿Cómo ver la ruta donde se almacenan los volumenes anonimos?

### Validar la ruta del root de Docker

		docker info | grep -i root

Esto nos data la ruta del root de Docker, para acceder lo podemos hacer mediante sudo

		cd /var/lib/docker

Accedemos como sudo
					
		sudo su

Ahora podremos acceder a la carpeta volume, dentro de sta carpeta hallaremos la carpeta del volumen con el ID del contenedor.


  
