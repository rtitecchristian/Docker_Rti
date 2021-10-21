para usar el Docker-compose de cerbot modifique el archivo defaul de nginx 
listen 443;
    #Aquí deberás introducir el nombre de tu dominio.
    xpos.rtitec.com;

    #Aquí deberás especificar la ruta de tu certificado SSL
    ssl_certificate           /root/volumen/cerbot/certbot/conf/csr;
    ssl_certificate_key       /root/volumen/cerbot/certbot/conf/keys;

    ssl on;
    ssl_session_cache  shared:SSL:10m;
    ssl_protocols  TLSv1 TLSv1.1 TLSv1.2 TLSv1.3;
    ssl_ciphers EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH;

    ssl_prefer_server_ciphers on;
    ssl_session_timeout  10m;

    access_log            /var/log/nginx/midominio.com.access.log;