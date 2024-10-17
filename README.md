# Tarea 3

La siguiente práctica es una lista de tareas que tenéis que hacer. 

Por cada tarea tenéis que ir poniendo los comandos utilizados y, brevemente, describir el proceso y como compruebas que se ha realizado lo pedido en un fichero (nombre "Readme.md") con formato markdown.

Crear un repositorio en github para subir este fichero

Cada dos apartados tenéis que hacer un commit nombrando el numero del apartado

En la respuesta pon el enlace a tu repositorio en github

Utiliza la imagen de **Apache**, tag 2.4 y apoyandote en la **mini guía** de docker sigue las instrucciones:

---
## 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.
```bash
docker pull httpd:2.4
docker images
```
![tarea3-1](https://github.com/user-attachments/assets/9183239f-5608-48d3-81ec-351bb207bfde)


## 2. Crea un contenedor con el nombre 'dam_web1'.
```bash
docker container create -i -t --name dam_web1 httpd:2.4
```
![TAREA3-2](https://github.com/user-attachments/assets/71edbffe-7b2c-498f-90ff-b2581e715b57)


## 3. Si quieres poder acceder desde el navegador de tu equipo, ¿que debes hacer?
Utiliza bind mount para que el directorio del apache2 'htdocs' esté montado un directorio que tu elijas.
```bash
docker run -d --name dam_webPrueba1 -p 8000:80 -v /home/adrian/miCarpeta:/usr/local/apache2/htdocs httpd:2.4
```

## 4. Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.
Una vez instalado el **SSH** que necesitaremos para hacer la prueba: 

Ahora crearemos nuestro **HolaMundo.html** dentro de nuestra ruta **/home/adrian/miCarpeta**(el directorio se creo durante el comando del punto3):
```bash
 <html>
     <head>
         <title>Hola Mundo</title>
     </head>
     <body>
         <h1>Hola Mundo</h1>
     </body>
 </html>
```
Y por último comprobamos con nuestro navegador web, introduciendo nuestra IP que hemos sacado con **ip a** y utilizando el puerto que hemos asignado **8000**
En este caso: **http://10.0.9.154:8000/HolaMundo.html**

![holamundo](https://github.com/user-attachments/assets/c4c40c8c-2a84-4c6f-9d2a-aaf9873e4f9e)




## 5. Crea otro contenedor 'dam_web2' con el mismo bind mount y a otro puerto, por ejemplo 9080.
```bash
docker run -d --name dam_webPrueba2 -p 9000:80 -v /home/adrian/miCarpeta:/usr/local/apache2/htdocs httpd:2.4
```

## 6. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:
http://localhost:9080 

http://localhost:8000
```bash

```

## 7. Realiza modificaciones de la página y comprueba que los dos servidores 'sirven' la misma página
```bash

```







