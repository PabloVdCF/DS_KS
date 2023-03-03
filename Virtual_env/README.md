# Entorno Virtual para Windows

Existen varias formas de crear entornos virtuales:
## Para crear un entorno virtual con una versión específica de Python en Windows.

> En mi caso utilizaré la versión 3.10 que será actualmente la compatible para el uso de **Kedro**

1. Descargar e instalar la versión de Python 3.10 para Windows desde el sitio web oficial de Python: https://www.python.org/downloads/release/python-310/.
  * Para saber donde tenemos instalado python, abrimos la terminal (CMD) y ejecutamos
  ````cmd
  where python
  ````
2. Abre la terminal de línea de comandos de Windows (CMD) y ejecuta el siguiente comando para instalar la herramienta de creación de entornos virtuales "virtualenv" si aún no lo ha hecho:

````shell
pip install virtualenv
````

3. Crea un nuevo entorno virtual con Python 3.10 usando el siguiente comando:

````shell
virtualenv -p C:\Python310\python.exe myenv
````
-p es el path donde está instalado la versión de python

4. Esto creará un nuevo entorno virtual llamado "myenv" en el directorio actual con Python 3.10.
Active el entorno virtual con el siguiente comando:

````shell
.\myenv\Scripts\activate
````
Esto activará el entorno virtual y cambiará la línea de comandos para mostrar el nombre del entorno virtual activado.

5. Ahora puedes instalar y ejecutar aplicaciones y paquetes de Python dentro de este entorno virtual, que utiliza Python 3.10. Para salir del entorno virtual, simplemente escribe `deactivate` en la línea de comandos.

- Si no tienes permisos para instalar paquetes, puedes escribir el siguiente comando en **PowerShell**

````shell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process 
````

![DoggoTypingGIF](https://user-images.githubusercontent.com/113723139/222743720-9fbc1bae-d540-45ab-81b8-aacf35ef0585.gif)
