CONTENEDOR DOCKER DE LETSENCRYPT 
Este contenedor incluye un nginx proxy, no se como configurar el lado de nginx para que funcione
en el archivo original del compose tiene esta linea de otro nginx que se peude agregar variso virtual host 
***************************************************************************************************************
  www:
    image: nginx
    restart: always
    expose:
      - "80"
    volumes:
      - /Users/dir1/varios/1/www:/usr/share/nginx/html:ro
    environment:
      - VIRTUAL_HOST=dominio.com,www.dominio.com
      - LETSENCRYPT_HOST=dominio.com,www.dominio.com
      - LETSENCRYPT_EMAIL=mail@dominio.com
    depends_on:
      - nginx-proxy
      - letsencrypt
	  
*********************************************************************************************************************	  