# Computer Assisted Audit Techniques - Ejemplos de uso

## Demo: uso de la herramienta Sonarqube

Para este demo se va a usar Docker. Entonces conviene tenerlo instalado antes de comenzar se comparte el siguiente enlace a su tutorial oficial de instalación.

* Instalar docker. [Tutorial](https://docs.docker.com/get-docker/)

El demo también podría ser ejecutado sin contar con Docker, aunque en ese caso se debería contar con la herramienta Sonarqube en otro medio de instalación.

### Obtener la imagen

~~~ bash
docker pull sonarqube
~~~

### Generar el contenedor

~~~ bash
docker run --rm --name sonarqube -p 9000:9000 sonarqube
~~~

Considerar que la opción `--rm` hace que el contenedor sea eliminado una vez cerrado o detenido, con lo que se perderán los datos del análisis. En este caso se podría usar si esa opción para que los datos persistan en el contenedor.

### Consideraciones previas

Se va a analizar un proyecto de muestra con código Python / PHP. El mismo se encuentra en la carpeta **codigo**.

### Pasos a seguir

1. Ingresar en el navegador a la [aplicación](http://localhost:9000/)
2. Login con las credenciales por defecto **admin : admin**
3. Generar un nuevo proyecto:
   * Definir un nombre
   * Generar un token
   * Seleccionar lenguaje y sistema operativo (SO)
   * Descargar la versión correspondiente a su SO del **sonar-scanner**, el link se puede obtener desde la misma herramienta en la interfaz web
4. Ejecutar sonar-scanner en la carpeta donde se encuentre el código fuente a analizar (ver cómo se alcanza al archivo ejecutable que se encuentra en /bin de la carpeta de instalación del scanner)
5. Una vez que termine la ejecución, volver al navegador y ver los resultados del proyecto
6. Generar el reporte del uso de la herramienta para el registro de las evidencias que se encuentren

### Apagado del contenedor

~~~ bash
docker stop sonarqube
~~~

## Referencias

[Fuente de la imagen](https://hub.docker.com/_/sonarqube/)  
[Más información sobre la herramienta](https://www.sonarqube.org/)
[Repositorio de código de ejemplo](https://github.com/genack/gPOS)
