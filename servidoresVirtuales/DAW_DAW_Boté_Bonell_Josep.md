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

Ahora debemos crear los archivos de configuración de los servidores, uno se llamará daw.conf y el otro, jboteb.conf, para crear los ficheros podemos usar de referencia el archivo 000-default.conf:

```
cp /etc/apache2/sites-avaiable/000-default.conf /etc/apache2/sites-avaiable/daw.conf
cp /etc/apache2/sites-avaiable/000-default.conf /etc/apache2/sites-avaiable/jboteb.conf
```

Hay que editar algunas líenas de los ficheros para que funcione correctamente:

* daw.conf
```
ServerName daw.gimbernat.eug.es
DocumentRoot /var/www/daw/

SSLEngine on
SSLCertificateFile /etc/apache2/ssl/daw.crt
SSLCertificateKeyFile /etc/apache2/ssl/daw.key

<Directory /var/www/daw/>
    Options Indexes FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
```

* jboteb.conf
```
ServerName jboteb.gimbernat.eug.es
DocumentRoot /var/www/jboteb/

SSLEngine on
SSLCertificateFile /etc/apache2/ssl/jboteb.crt
SSLCertificateKeyFile /etc/apache2/ssl/jboteb.key

<Directory /var/www/jboteb/>
    Options Indexes FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
```

En caso de no tener el certificado ssl debemos instalarlo y crearlo:

1. Instalamos el módulo:
   ```
   sudo a2enmod ssl
   sudo systemctl restart apache2
    ```
2. Creamos el directorio para crear los certificados ssl:
   ```
   sudo mkdir /etc/apache2/ssl
   ```
3. Generamos el .cert i el .key usando OpenSSL:
   ```
   sudo openssl req -x509 -nodes -days 365 -newkey rsa:3072 -keyout /etc/apache2/ssl/daw.key -out /etc/apache2/ssl/daw.crt

   sudo openssl req -x509 -nodes -days 365 -newkey rsa:3072 -keyout /etc/apache2/ssl/jboteb.key -out /etc/apache2/ssl/jboteb.crt
   ```

Finalmente solo debemos añadir estas líneas al fichero /etc/hosts:

```
127.0.0.1 daw.gimbernat.eug.es
127.0.0.1 jboteb.gimbernat.eug.es
```

Y para acabar hablilitamos los sitios y reiniciamos apache:

```
sudo a2ensite daw.conf
sudo a2ensite jboteb.conf  
sudo systemctl restart apache2
```

# Resultados:

![image](https://github.com/pepbote/daw-pruebas/assets/144775358/b930a364-891a-4874-8006-8c7ee4057bbf)

![image](https://github.com/pepbote/daw-pruebas/assets/144775358/9a84433b-e05d-43e7-bd6a-13ec3943beb1)
