# Webgrabplus-EPG-Docker

Docker de la imagen ghcr.io/linuxserver/webgrabplus para monitorizar el EPG de canales de todo el mundo.
## Configuracion
El archivo de configuracion se ubica en *config/WebGrab++.config.xml*
``` yml
    <!-- Ubicacion donde se generara el epg en formato xml. -->
    <filename>/data/guide.xml</filename>
    
    <!-- Modo de grabacion, en este caso mide el tiempo de cada programa actualizado o nuevo programa agregado -->
    <mode>m</mode>
    
    <!-- Bot que se encargara de acceder a los sitios web a capturar los datos. -->
    <user-agent>Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36 Edg/79.0.309.71</user-agent>
    
    <!-- Key para desencripar archivos ini de canales encriptados por desarrolladores -->
    <!-- <decryptkey site="movistarplus.es"></decryptkey> -->
    
    <!-- Licencia de tu usuario de webgrap para activar la licencia postdonacion -->
    <license wg-username="tonomolla6" registered-email="tonomollag6@gmail.com" password="" />
    
    <!-- Registrar el programa -->
    <logging>on</logging>
    
    <!-- El valor del elemento es el número de veces que el motor volverá a intentar capturar una página -->
    <retry time-out="5">4</retry>
    
    <!-- El período de tiempo para el que se tomarán los programas. -->
    <timespan>0</timespan>
    
    <!-- El modo de captura de datos, ahora mismo tenemos f, para que sustituya el epg por uno nuevo, puede ser incrementar y tener un registro de meses... -->
    <update>f</update>
```

Para mas informacion en la documentacion oficial estan todas las opciones.
http://webgrabplus.com/documentation/configuration/webgrabconfigxml
## Ejecutar el servicio
1. Clonamos el repositorio.
    ``` sh
        git clone https://github.com/tonomolla6/Webgrabplus-EPG-Docker.git
    ```
2. Accedemos al repositorio y ejecutamos el archivo *docker-compose.yml* con docker compose.
    ``` sh
        sudo docker-compose up
    ```