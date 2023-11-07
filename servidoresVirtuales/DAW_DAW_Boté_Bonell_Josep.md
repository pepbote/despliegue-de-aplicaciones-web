Primero creamos dos directorios en /var/www, uno con cada nombre que nos pide el ejercicio:

    mkdir /var/www/daw 
    mkdir /var/www/jboteb
    
estos serán los directorios raíz de nuestros servidores, aquí debemos poner dentro de cada directorio el archivo html y el css que queremos que se visualize, debería querdar algo así:

    ls /var/www/daw
        index.html style.css
    ls /var/www/jboteb
        index.html style.css

En esta actividad debemos poner en el ./daw/index.html el nombre de la clase y en el ./daw/style.css algún estilo para el texto, en el index.html de jboteb debemos poner nuestro currículum y después cambiarle algún estido.

    nano /var/www/daw/index.html
   
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/f728cf07-f2aa-49fb-80b8-5f145ff379a8)

    nano /var/www/daw/style.css

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/68e051c3-8ce4-49d8-925d-c4707332e87d)

    nano /var/www/jboteb/index.html

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/2affabb3-2e22-49b7-bdb0-caa429db1564)

    nano /var/www/jboteb/style.css

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/0b09af70-4250-4eae-a395-6c124c88b28b)


