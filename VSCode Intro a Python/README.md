

## Prerrequisitos
* Capacidad de instalar programas localmente.
* Conocimientos sobre cómo abrir y ejecutar comandos desde una ventana de comando o terminal.
* Conocimientos básicos de programación.

## ¿Cómo puedo saber si ya tengo instalado Python 3 en mi equipo?
Es posible que el equipo ya tenga instalado Python 3. A veces, hay aplicaciones que instalan Python 3 sin que lo sepa.

En la parte superior de esta página, seleccione la pestaña que corresponda a su sistema operativo.

Windows
Para determinar si su equipo Windows ya tiene instalado Python 3:

Para abrir la aplicación del símbolo del sistema, vaya a Inicio en la barra de tareas de Windows.

Escriba cmd en el cuadro de búsqueda de Windows y seleccione la aplicación Símbolo del sistema en la sección Mejor coincidencia de los resultados.

Escriba el comando siguiente y presione Entrar:

Consola

Copiar
python --version
or

Consola

Copiar
py --version
 Nota

La ejecución de python --version o py --version puede no devolver un valor, o bien puede devolver un mensaje de error que indica "py" is not recognized as an internal or external command, operable program or batch file ("py" no se reconoce como un comando interno o externo, un programa ejecutable o un archivo por lotes). Esto indica que Python no está instalado en el sistema Windows.

Si se muestra la palabra Python seguida de un conjunto de números separados por puntos (.), significa que tiene instalada una versión de Python. Este es un ejemplo de la salida que podría obtener:

Resultados

Copiar
    Python 3.10.0
Si el primer número es 3, Python 3 está instalado en el equipo. Aunque no disponga de la versión más actualizada, podrá seguir todos los módulos de Python para principiantes en Microsoft Learn.

Si el primer número es 2 o ha recibido un mensaje de error, deberá instalar Python 3. En la siguiente unidad, le guiaremos por la instalación de Python 3.

Resumen
Las principales conclusiones de esta unidad son:

Ya no se debe usar la versión 2 de Python. Todo el código nuevo debe escribirse con la versión 3 de Python.
Use la marca --version de Python para asegurarse de que sabe con qué versión está trabajando.
