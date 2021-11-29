# Internet-de-las-Cosas
2da Actividad Calificada

# Building the Critical Components


## Docker-compose

Para el desarrollo de “Build Your Own IoT Platform” se levanto los servicios de:

[![N|Node-red](https://i.ibb.co/Q62QZpv/logoigm1.png)](https://nodered.org/) [![N|Mosquitto](https://i.ibb.co/g7rhrjM/logoigm2.png)](https://mosquitto.org/) [![N|MySql](https://i.ibb.co/PjLxDCC/logoigm3.png)](https://www.mysql.com/) [![N|phpMyAdmin](https://i.ibb.co/cypsdgy/logoigm4.png)](https://www.phpmyadmin.net/)

En la ruta ./ raíz del repositorio podrá encontrar el archivo docker-compose.yml, este archivo contendrá los 4 servicios ya antes mencionados, podrá encontrar etiquetas por cada servicio como

 - Image: Nombre de la imagen a descargar desde dockerhub.
Container_name: Nombre para identificar al contenedor con el servicio
 - Networks: Esta configuración permitirá tener a todos los contenedores que lo posean conexión y visibilidad entre ellos.
 - Ports: Esta etiqueta mapea tanto el puerto del contenedor como el de nuestra máquina local, para poder acceder sin problemas.
 - Configuración de base de datos: Aquí existen varias variables de configuración como las contraseñas y usuarios para la base de datos.

luego de analizar nuestro yml procedemos a ejecutar con el siguiente comando este archivo

![N|Img1](https://i.ibb.co/5x8hJWw/igm1.png)

Luego podremos observar los 4 servicios funcionando si todo va bien, se usa el siguiente comando:

![N|Img2](https://i.ibb.co/wRtj6WD/igm2.png)

## Verificación de los diferentes servicios

### MySQL y phpMyAdmin
![N|Img3](https://i.ibb.co/6n0s57H/igm3.png)
### Node-Red
![N|Img4](https://i.ibb.co/khZvTN2/igm4.png)
## Desarrollo de actividades del capítulo 7
A continuación se presentan las actividades con su respectiva ruta en nuestro repositorio donde encontrará los archivos JSON donde contienen la mayoría de configuraciones para poder importarlo en el servicio de Node-Red para replicarlo con mayor facilidad

 - Creación de base de datos para próximos ejercicios
Ruta:  ./database/tSeriesDB.sql
 - Creando el primer flujo para nuestra plataforma
Ruta: ./json/0_intro.json ![N|Img5](https://i.ibb.co/3BwzqDq/igm11.png)
 - Adición de la capacidad de publicación de MQTT
Ruta: ./json/1_TimeStamp.json
 - Publicador de mensajes de API REST
 - ![N|Img3](https://i.ibb.co/GTkdrfL/igm12.png)
En este ejercicio se logró replicar la arquitectura del servicio en node-red, lamentablemente el servicio en la nube que se usaba para obtener respuestas o mensajes, dejó de funcionar por lo cual solo se llegó hasta este punto.
Ruta: ./json/2_rest_api.json
![N|Img3](https://i.ibb.co/PTRFHPK/igm5.png)
 - Configurar el nodo de entrada MQTT e implementar
Ruta: ./json/3_sql_a.json
![N|Img3](https://i.ibb.co/TM1LdV5/igm6.png)
 - Agregue y configure el nodo MySQL con nuestras credenciales de base de datos de series de tiempo
Ruta: ./json/4_sql_b.json
![N|Img3](https://i.ibb.co/X87R9CY/igm7.png)
Luego de ejecutar este servicio, se detectó el almacenamiento en la base de datos configurada, donde se guardaron los siguientes datos:
![N|Img3](https://i.ibb.co/cNXgQVD/igm8.png)
 - Recuperador de mensajes de la API REST
Lamentablemente este ejercicio usa una dirección donde el servicio que escucha ya no está en línea, por lo cual se logró replicar la estructura pero no se pudo realizar las peticiones.
Ruta: ./json/5_retriever.json
![N|Img3](https://i.ibb.co/rvjc8sd/igm9.png)
 - Ejecución de Node-RED en segundo plano continuamente
Para este ejercicio debíamos ingresar al contenedor para poder instalar una instancia de una libreria “forever”, se logro listar el servicio de mosquito:
![N|Img3](https://i.ibb.co/mCkyDKt/igm10.png)
