# GIT

Git es un sistema de control de versiones distribuido, lo que significa que un clon local del proyecto es un repositorio de control de versiones completo. Estos repositorios locales plenamente funcionales permiten trabajar sin conexión o de forma remota con facilidad.

## ¿Qué es el control de versiones?

Un sistema de control de versiones (VCS) es un programa o conjunto de programas que realiza un seguimiento de los cambios en una colección de archivos.
Uno de los objetivos de un VCS es recuperar fácilmente versiones anteriores de archivos individuales o de todo el proyecto. 
Otro objetivo es permitir que varios miembros de un equipo trabajen en un proyecto, incluso en los mismos archivos, al mismo tiempo sin que eso afecte al trabajo de los demás.
  
Otro nombre para un VCS es un sistema de administración de configuración de software (SCM). Los dos términos suelen usarse indistintamente;
de hecho, la documentación oficial de Git se encuentra en git-scm.com. Técnicamente, el control de versiones es solo uno de los procedimientos 
que implica el SCM. Un VCS se puede usar para otros proyectos, además de los de software, incluidos libros y tutoriales en línea.


Con un VCS, puede:

* Ver todos los cambios realizados en el proyecto, cuándo se hicieron los cambios y quién los efectuó.
* Incluir un mensaje con cada cambio para explicar los motivos.
* Recuperar versiones anteriores del proyecto completo o de archivos individuales.
* Crear ramas, donde los cambios se pueden hacer experimentalmente. Esta característica permite que se trabaje en varios conjuntos de cambios diferentes (por ejemplo, características o correcciones de errores) al mismo tiempo, posiblemente personas distintas, sin que ello afecte a la rama principal. Más adelante se pueden combinar los cambios que se quieren mantener en la rama principal.
* Adjuntar una etiqueta a una versión, por ejemplo, para marcar una nueva versión.

## Control de versiones distribuido

Las instancias anteriores de los VCS, como CVS, Subversion (SVN) y Perforce, usaban un servidor centralizado para almacenar el historial de un proyecto.
Esta centralización significaba que un solo servidor también era un único punto de error en potencia.

Git es un sistema distribuido, lo que significa que el historial completo de un proyecto se almacena en el cliente y en el servidor. 
Se pueden editar archivos sin conexión de red, protegerlos localmente y sincronizarlos con el servidor cuando una conexión esté disponible. 
Si un servidor deja de funcionar, todavía tendrá una copia local del proyecto. Técnicamente, ni siquiera es necesario tener un servidor. 
Los cambios pueden pasarse por correo electrónico o compartirse mediante medios extraíbles, pero, en la práctica, nadie usa Git así.

## Terminología de Git

* **Árbol de trabajo**: conjunto de directorios y archivos anidados que contienen el proyecto en el que se trabaja.

* **Repositorio (repo)**: directorio, situado en el nivel superior de un árbol de trabajo, donde Git mantiene todo el historial 
y los metadatos de un proyecto. A veces se hace referencia a los repositorios como repos. Un repositorio vacío es aquel que no forma parte 
de un árbol de trabajo; se usa para compartir o realizar copias de seguridad. Un repositorio vacío suele ser un directorio con un nombre que 
acaba en .git, por ejemplo, project.git.

* **Hash**: número generado por una función hash que representa el contenido de un archivo u otro objeto como un número de dígitos fijo. 
Git usa hashes de 160 bits de longitud. Una ventaja de usar códigos hash es que Git puede indicar si un archivo ha cambiado aplicando 
un algoritmo hash a su contenido y comparando el resultado con el hash anterior. Si se cambia la marca de fecha y hora del archivo, 
pero el hash del archivo no, Git sabe que el contenido del archivo no se ha modificado.

* **Objeto**: un repositorio de Git contiene cuatro tipos de objetos, cada uno identificado de forma única por un hash SHA-1. 
Un objeto blob contiene un archivo normal. Un objeto árbol representa un directorio, y contiene nombres, valores hash y permisos. 
Un objeto de confirmación representa una versión específica del árbol de trabajo. Una etiqueta es un nombre asociado a una confirmación.

* **Confirmación**: cuando se usa como verbo, confirmar significa crear un objeto de confirmación. Esta acción toma su nombre de las 
confirmaciones en una base de datos. Significa que se confirman los cambios realizados para que otros usuarios también puedan verlos.

* **Rama**: serie con nombre de confirmaciones vinculadas. La confirmación más reciente en una rama se denomina nivel superior. 
La rama predeterminada, que se crea al inicializar un repositorio, se denomina `main`, y suele tener el nombre master en Git. 
El nivel superior de la rama actual se denomina `HEAD`. Las ramas son una característica increíblemente útil de Git porque permiten 
a los desarrolladores trabajar de forma independiente (o conjunta) en ramas y luego combinar los cambios en la rama predeterminada.

* **Remoto**: referencia con nombre a otro repositorio de Git. Cuando se crea un repositorio, Git crea un remoto denominado `origin`, 
que es el remoto predeterminado para las operaciones de envío e incorporación de cambios.

* **Comandos, subcomandos y opciones**: las operaciones de Git se realizan mediante comandos como `git push` y `git pull`. 
git es el comando, mientras que push o pull es el subcomando. El subcomando especifica la operación que quiere que Git realice. 
Los comandos suelen ir acompañados de opciones, que usan guiones (-) o guiones dobles (--). Por ejemplo, git reset --hard.

## Configuración de Git

1. En Cloud Shell, para comprobar que Git está instalado, escriba git --version:

````bash
git --version
````
>Consejo:
Puedes usar el botón Copiar para copiar los comandos en el Portapapeles. Para pegarlos, haga clic con el botón derecho en una nueva línea en el terminal 
de Cloud Shell y selecciona Pegar, o bien usa el método abreviado de teclado Mayús+Insert (⌘+V en macOS).

2. Deberías ver una salida similar a la de este ejemplo:
Resultados
````bash
git version 2.7.4
````
3. Para configurar Git, debes definir algunas variables globales: `user.name` y `user.email`. Ambas son necesarias para realizar confirmaciones.

4. Pon tu nombre en Cloud Shell con el siguiente comando. Reemplaza <USER_NAME> por el nombre de usuario que quiere usar.
````bash
git config --global user.name "<USER_NAME>"
````
5. Ahora, usa este comando para crear una variable de configuración `user.email`; para ello, reemplaza <USER_EMAIL> por tu dirección de correo electrónico:
````bash
git config --global user.email "<USER_EMAIL>"
````
6. Ejecuta el siguiente comando para comprobar que los cambios han funcionado:
````bash
git config --list
````
7. Confirma que la salida incluye dos líneas similares al siguiente ejemplo. El nombre y la dirección de correo electrónico serán distintos 
a los que se muestran en el ejemplo.

Resultados
````bash
user.name=User Name
user.email=user-name@contoso.com
````

## Configuración del repositorio de Git

Git funciona buscando cambios en los archivos dentro de una determinada carpeta. Vamos a crear una carpeta que actúe como árbol de trabajo
(directorio del proyecto) y a permitir que Git sepa sobre ella para que pueda comenzar a seguir los cambios. Se indica a Git que empiece
a realizar el seguimiento de los cambios mediante la inicialización de un repositorio de Git en esa carpeta.

Empieza por crear una carpeta vacía para el proyecto y luego inicializa un repositorio de Git dentro de ella.

1. Crea una carpeta con el nombre Cats. Esta carpeta va a ser el directorio del proyecto, también denominado árbol de trabajo. 
El directorio del proyecto es donde se almacenan todos los archivos relacionados con el proyecto. 
En este ejercicio, es donde se almacenan el sitio web y los archivos que crean el sitio web y su contenido.

````Bash
mkdir Cats
````
2. Vete al directorio del proyecto mediante el comando `cd`:

````Bash
cd Cats
````
3. Ahora, inicializa el nuevo repositorio y establece el nombre de la rama predeterminada en `main`:

Si está ejecutando la versión 2.28.0 o una posterior de Git, use los comandos siguientes:

````Bash
git init --initial-branch=main
git init -b main
````

En versiones anteriores de Git, use estos comandos:

````Bash
git init
git checkout -b main
````
Después de ejecutar el comando de inicialización, deberías ver una salida similar a la de este ejemplo:

Resultados
````bash
Initialized empty Git repository in /home/<user>/Cats/.git/

Switched to a new branch 'main'
````
4. Ahora, usa un comando `git status` para mostrar el estado del árbol de trabajo:

````Bash
git status
````
Git responde con esta salida, que indica que master es la rama actual. (De hecho, también es la única rama). Por ahora todo está claro.

Resultados
````bash
 On branch master

 No commits yet

 nothing to commit (create/copy files and use "git add" to track)
````  
5. Use un comando `ls` para mostrar el estado del árbol de trabajo:

````Bash
ls -a
````
Confirma que el directorio contiene un subdirectorio denominado .git. (El uso de la opción `-a` con `ls` es importante, 
ya que Linux normalmente oculta los nombres de archivos y directorios que comienzan con un punto). Esta carpeta es el repositorio de Git: 
El directorio en el que Git almacena los metadatos y el historial del árbol de trabajo.

Normalmente, no se hace nada directamente con el directorio .git. Git actualiza los metadatos a medida que el estado del árbol 
de trabajo cambia para mantener un seguimiento de lo que ha cambiado en sus archivos. Este directorio es práctico para usted, 
pero es increíblemente importante para Git.

## Comandos básicos de Git

Git recuerda los cambios efectuados en los archivos como si tomara instantáneas del sistema de archivos.

**git status**
El primer comando de Git, y el que se usa con más frecuencia, es git status.
git status muestra el estado del árbol de trabajo. Permite ver los cambios que Git está siguiendo en ese momento para poder decidir si quiere pedir a Git que tome otra instantánea.

**git add**
git add es el comando que se usa para indicar a Git que empiece a realizar un seguimiento de los cambios en determinados archivos.

El término técnico es almacenamiento provisional de estos cambios. Vas a usar git add para almacenar provisionalmente los cambios a fin de prepararte para una confirmación. Todos los cambios en los archivos que se han agregado, pero que aún no se han confirmado, se almacenan en el área de almacenamiento provisional.

**git commit**
Después de haber almacenado provisionalmente algunos cambios para su confirmación, puede guardar el trabajo en una instantánea si invoca al comando git commit.

Confirmar (o "commit") es un verbo y un sustantivo. Básicamente, tiene el mismo significado que cuando se confirma en un plan o se confirma un cambio en una base de datos. Como verbo, la confirmación de cambios significa que se coloca una copia (del archivo, el directorio u otra "cosa") en el repositorio como una nueva versión. Como sustantivo, una confirmación es el pequeño fragmento de datos que asigna una identidad única a los cambios que se confirman. Los datos que se guardan en una confirmación incluyen el nombre del autor y la dirección de correo electrónico, la fecha, los comentarios sobre lo que se ha hecho (y por qué), una firma digital opcional y el identificador único de la confirmación anterior.

**git log**
El comando git log permite ver información sobre las confirmaciones anteriores. Cada confirmación tiene un mensaje adjunto (un mensaje de confirmación), y el comando git log permite imprimir información sobre las confirmaciones más recientes, como su marca de tiempo, el autor y un mensaje de confirmación. Este comando ayuda a realizar un seguimiento de lo que ha estado haciendo y de los cambios que se han guardado.

**git help**
Ya ha probado el comando git help, pero vale la pena recordar ciertas cosas. Use este comando para obtener información fácilmente sobre todos los comandos que conoce hasta ahora y más.

> Recuerda que cada comando incluye también su propia página de ayuda. Para encontrar estas páginas de ayuda, escriba git <command> --help. Por ejemplo, git commit --help muestra una página que proporciona más información sobre el comando git commit y cómo usarlo.
