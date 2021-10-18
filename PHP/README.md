PARA CORRER EL CONTENEDOR DE PHP USE LA SIGUEINTE LINEA
docker run -p 9000:80 -d -v /var/www/html/:/var/www/html/ php:7.4-alpine3.14

solo para prueba, quedo en deshuso porque se incluyo en el dockercompose de mysql 

CONFIGURACION DE NGINX EN LINUX
vim /etc/nginx/sites-enabled/default

habilite las lineas de php
en lugar de usar socket voy a usar tcpip 
uso la linea fastcgi_pass 172.17.0.2:9000; 
la ip la saque ejecutando
docker container inspect "idcontenedor" me muestra la ip del servidor php
