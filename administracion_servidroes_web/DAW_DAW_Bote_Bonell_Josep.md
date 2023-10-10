# Exercici 1
Instale en una máquina virtual un sistema operativo con base Linux (se recomienda Debian o Ubuntu) e instale apache2.

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/39c20703-019b-4d9a-9fd3-1a0e825efd2f)

# Exercici 2
Explique con sus palabras que es una petición GET, POST, PUT y DELETE, remarcando sus diferencias. 

# Exercici 3
Cambie del puerto 80 al puerto 4444 el servidor apache2. Muestra desde el navegador su funcionamiento adjuntando una captura de pantalla. 

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/74a1bd75-2703-4c01-aa6b-439a87d1396b)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/be42b463-e386-412a-a359-a6c8819ed54e)

# Exercici 4
Instale un certificado SSL y configure su Apache para servir contenido a través de HTTPS en el puerto 4444. Muestre desde el navegador cómo se muestra el sitio web como "seguro" (aunque sea un certificado autofirmado).

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/e8f56110-9c37-4963-90d2-980c93262fe8)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/52cb5383-2499-4b9b-832d-8df57ad0acc2)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/f07eef2d-bc08-4b1e-a633-946cca82edbb)

![image](https://github.com/pepbote/despliegue-de-aplicaciones-web/assets/144775358/2e965e0b-f049-420c-8d6e-78bcced7de02)

# Exercici 5
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
# Exercici 6
# Exercici 7
