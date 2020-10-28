# Demo 2 - Python + Jupyter + Pandas

[Fuente de la imagen](https://hub.docker.com/r/jupyter/scipy-notebook/)  
[Documentación](http://jupyter-docker-stacks.readthedocs.io/en/latest/index.html)

## Obtener la imagen desde la red local

~~~ bash
docker pull IP:5000/demo2python
~~~

## Generar el contenedor

~~~ bash
docker run --name calidad_datos -p 8888:8888 -v $PWD:/home/jovyan/work 172.16.7.200:5000/demo2python
~~~

**Recomendación:** es conveniente ejecutar esta instrucción estando posicionado sobre un directorio desde el que se pueda llegar a la carpeta donde se encuentran estos archivos.

## Consideraciones previas

Se va a analizar un dataset obtenido a partir de una base de datos a auditar utilizando para ello una serie de evaluaciones implementadas en lenguaje Python dispuestas en una libreta Jupyter. El dataset se encuentra en la carpeta **datasets** y las libretas en la carpeta **libretas**.

Por otra parte, en la carpeta **docs** se encuentra la documentación de referencia que representa el conocimiento del dominio sobre el cual está basado el dataset. Además, encontrarán un archivo en el que se registrarán los resultados encontrados en el anáisis.

## Pasos a seguir

1. Cuando inicia el contenedor con Jupyter al final muestra una URL a utilizar, acceder a ella desde el navegador web
2. Ingresar a la carpeta **work** en donde va a estar espejada la carpeta actual del demo
3. Abrir la libreta **[Calidad de datos](http://localhost:8888/tree/work/libretas/Calidad_de_datos.ipynb)**
4. Ejecutar las diferentes celdas de la libreta e ir documentando sus resultados
5. Generar el reporte del uso de la herramienta para el registro de las evidencias que se encuentren

## Apagado del contenedor

~~~ bash
Ctrl + C
~~~
