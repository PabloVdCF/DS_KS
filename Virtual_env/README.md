# Entorno Virtual para Windows

Existen varias formas de crear entornos virtuales:

## Windows

Con la herramienta de **Visual Studio Code** la abrimos y accedemos a la terminal **PowerShell**

1. Creamos una carpeta con el nombre del proyecto que vayamos a realizar
````shell
mkdir miproyecto
````
2. Para crear el entorno virtual ejecutamos:
````shell
py -m venv .\miproyecto\
````

3. Nos aseguraremos de que nos deje instalar paquetes con el código
````shell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process 
````

4. Ahora que tenemos permisos para instalar nos vamos a nuestra carpeta y activaremos el entorno virtual
````bash
cd .\miproyecto\Scripts\

.\activate
````
