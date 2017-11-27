# Configuraciones básicas y creación de dockers de prueba

## Primer paso
Debes construir un docker personalizado que incluye el servidor openssh

-Con nuestro Dockerfile construiremos la imagen de nuestros dockers. 

Usamos el siguiente comando en nuestra consola: 
               
               docker build -t server:16.04 .

## Segundo paso, despliege

Ahora debes crear una maquinas para el despliegue, se creará  un servidor Apache.

Usamos el siguiente comando en nuestra consola: 

docker run -d -P --name munin_web_server -p 2221:22 -p 80:80 server:16.04 

# tercer paso,Adicionar las llaves ssh</h3>

Usamos los siguientes comandos en nuestra consola: 

ssh -o StrictHostKeyChecking=no root@127.0.0.1 -p 2221 -i key.private hostname


## Cuarto paso, confirmación
Realiza una prueba de conexión a la maquina que se creó recientemente.

    ssh root@172.168.0.1 -p 2221 -i ../key.private

Si la conexión se establece, ya está listo el banco de pruebas y puedes ingresar a ansible.




