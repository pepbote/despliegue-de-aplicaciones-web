# Ejercicio 1
Instale en una máquina virtual un sistema operativo con base Linux (se recomienda Debian o Ubuntu) e instale apache2.

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/39c20703-019b-4d9a-9fd3-1a0e825efd2f)


# Ejercicio 2
Explique con sus palabras que es una petición GET, POST, PUT y DELETE, remarcando sus diferencias. 
    - GET para obtener un recurso del servidor
    - POST para crear un recurso del servidor   
    - PUT para actualizar un recurso del servidor
    - DELETE para eliminar un recurso del servidor

# Ejercicio 3
Cambie del puerto 80 al puerto 4444 el servidor apache2. Muestra desde el navegador su funcionamiento adjuntando una captura de pantalla. 

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/74a1bd75-2703-4c01-aa6b-439a87d1396b)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/be42b463-e386-412a-a359-a6c8819ed54e)


# Ejercicio 4
Instale un certificado SSL y configure su Apache para servir contenido a través de HTTPS en el puerto 4444. Muestre desde el navegador cómo se muestra el sitio web como "seguro" (aunque sea un certificado autofirmado).

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/e8f56110-9c37-4963-90d2-980c93262fe8)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/52cb5383-2499-4b9b-832d-8df57ad0acc2)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/f07eef2d-bc08-4b1e-a633-946cca82edbb)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/2e965e0b-f049-420c-8d6e-78bcced7de02)


# Ejercicio 5
¿Dónde se encuentran los ficheros de configuración de Apache2?
- Ubicación principal.
    - /etc/apache2
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/41f4b2f7-54da-401c-a54d-f38b0d02ceeb)

- Explora el archivo apache2.conf. Identifica las secciones principales y describe su propósito.
  1. ServerRoot: Establece la ubicación raíz de Apache2
  3. User y Group: Establecen los usuarios y los grupos donde se ejecutará el servidor Apache
  4. Timeout: Define el tiempo máximo que Apache esperará para recibir una solicitud del cliente antes de cerrar la conexión
  5. KeepAlive: Habilita o deshabilita el uso de conexiones Keep-Alive, que varia la velocidad de carga de las paginas web
  6. ServerTokens: Controla la información de las cabeceras http y de las páginas de error generadas por Apache
  7. PidFile: Especifica la ubicación del archivo que almacena el PID del servidor principal de Apache
  8. Directivas para la carga de módulos: Aqui se pueden habilitar módulos adicionales de Apache

- sites-available y sites-enabled: Explica la diferencia entre estos dos directorios y cómo funcionan juntos.
  1. Sites-available:
     - Es donde se guardan la configuración de todos los sitios web están disponibles, pero solo los que han sido habilitados mediante enlaces en sites-enabled. 
  2. Sites-enabled:
     - Habilita los sitios web mediante enlaces simbólicos, esto permite gestionar facilmente múltiples configuraciones de sistios web sin necesidad de modificar los archivos de Apache. 
    
- mods-available y mods-enabled: Explica la diferencia entre estos dos directorios.
     1. mods-available:
          - Contiene todalas las opciones de módulos disponibles.
     3. mods-enabled:
          - Contiene los módulos específicos que has activado para que Apache los utilize.

            
# Ejercicio 6
- Ubicación principal
- 
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/5976300e-d391-42f2-aacc-0c0aea52eec5)

- Control del servicio: Utiliza el binario de ejecución para iniciar, detener, recargar y reiniciar el servidor Apache2 explicando la diferencia entre cada uno de los comandos utilizados.
    - start: inicia el servidor si no está en ejecución
    - stop: detiene el servidor y lo apaga
    - reload: recarga la configuración sin detener el servidor
    - restart: detiene e inicia el servidor, se suele usar para reiniciar el servidor y aplicar cambios importantes en la configuración
      
- Comprobación de sintaxis: Usa el binario de Apache para verificar la sintaxis de tu configuración. Esto es útil para asegurarse de que no haya errores antes de reiniciar el servidor.

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/89a60122-4401-49bb-917f-bcac3224ef8b)


# Ejercicio 7
¿Dónde se encuentran los ficheros de monitorización de Apache2?
- Ubicación principal

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/87fd42c9-166f-40e4-846d-989122ed6e8e)

- error.log y access.log: Explica la diferencia entre estos dos archivos. Abre y revisa las entradas recientes en cada uno de ellos.
    - error.log: se usa para registrar los errores y advertencias relacionadas con el funcionamineto del servidor
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/36bee408-82a0-45c4-834c-b075b9c0ea4d)

    - access.log: se usa para registrar las solicitudes web exitosas
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/c2719d3e-fe4d-458e-85cb-e2680165e982)

- Rotación de logs: Investiga cómo funciona la rotación de logs en Apache2. ¿Por qué es importante? ¿Cómo se configura?
  
  La rotación de logs funciona de la siguiente manera:
    1. Renombra archivos de registro antiguos
    2. Crea un nuevo archivo de registro
    3. Comprime archivos antiguos
    4. Mantiene registros más manejables y ahorra espacio en disco
    5. Se configura en /etc/logrotate.d/apache2
  Es importante para conservar espacio en el disco, también facilita ala gestión y ánalisis de registros y mantiene un historial de registros

  ![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/7d808280-7cb4-46ca-8b88-2279a62c01aa)

- Monitorización en tiempo real: Utiliza herramientas como tail -f para monitorear en tiempo real los accesos a tu servidor web y posibles errores.
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/324fdf53-0972-48da-a37e-d389fc9ab3d5)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/e3d14341-9e8b-4a34-bf95-4d74156fbfa9)

- Análisis de logs: Instala y usa herramientas como goaccess para analizar y obtener estadísticas visuales a partir de tus logs de Apache2.

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/e27d8c01-562b-4575-a1ca-fb463edd09f8)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/6bda0d06-ce3d-4ab8-bf8d-ced571392850)



# Ejercicio 8
¿Qué es un Firewall? ¿Para qué sirve? ¿Por qué es necesario? Instale y configure un Firewall en la máquina virtual para que solo permita tráfico HTTP y HTTPS. Bloquee todo el resto de los puertos y demuestre su funcionamiento.

- Es una barrera de seguridad que controla el flujo de datos entre una red y mundo exterior. Define reglas para permitir o bloquear el tráfico, protegiendo contra amenazas cibernéticas y accesos no autorizados. Es muy importante para mantener la seguridad de los sistemas.

 ![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/992e984e-625a-4627-b193-d4a18aa8b194)
 
![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/d64b32e3-5e7e-4869-afd6-8cea77ec576c)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/5ab38e56-2920-446e-9c54-d454d240c379)

# Ejercicio 9
Explica con tus palabras las diferentes partes de una URL.

- Una URL se compone de un protocolo (como "https://"), un nombre de dominio que señala el servidor ("www.google.com"), y una ruta que indica la ubicación del recurso ("/pagina/directorio/"). Ocasionalmente, pueden agregarse parámetros y fragmentos para detalles adicionales o secciones específicas del recurso.

# Ejercicio 10
Explica el funcionamiento del protocolo HTTP con tus palabras.

- El protocolo de transferencia de hipertexto facilita ala comunicación entre navegadores y servidores web, cuando envías una solicitud http al servidor, responde enviando los datos de la página para que puedas verla en tu navegador.

# Ejercicio 11
¿Qué es un archivo .htaccess? Proporcione un ejemplo de cómo se puede utilizar
para reescribir URL o restringir el acceso a ciertas partes de su sitio web.

Es un archivo de configuración en servidores web Apache. Se puede utilizar para modificar la coonfiguración del servidor y aplicar directivas específicas a directorios o archivos. 

Por ejemplo para reescribir url se podría hacer así:
    
    RewriteEngine On
    RewriteRule ^pagina/([0-9]+)/?$ pagina.php?id=$1 [NC,L]

Esto reescribe la URL "tusitio.com/pagina/123" internamente como "tusitio.com/pagina.php?id=123":

También se puede restringir el acceso:
    
    Order Deny,Allow
    Deny from all
    Allow from 10.0.2.15
