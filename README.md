# Prework: Configuración de Entorno de Desarrollo en windows

La idea de este curso es que tu termines preparad@ para poder comenzar a aprender Desarrollo Web desde Cero.

Aquí vamos a configurar nuestro navegador, vamos a conocer que opciones de navegadores tenemos, también vamos a preparar nuestro editor de código, lo ideal es que aquí te estamos dejando list@ para tu camino como desarrollador@ web. Luego de esto nos vamos a pasar a ver algo super interesante que esl el Windows Subsystem for Linux, que basicamente te permite instalar un sistema operativo Linux dentro de tu Windows, que va a correr super rápido, super eficiente y eso te va a permitir ejecutar todas las herramientas de desarrollo, y no vas a tener un bloqueo para desarrollar nada, todo va a ir fluyendo. Vamos a dejar bien configurado nuestro WSL. Luego de esto hablaremos brevemente de Git y GitHub.

En caso de que tu no tengas una computadora con windows 10, no importa, pues puedes aprender a montar una maquina virtual de linux. Utilizando el sistema operativo Ubuntu.

Si no quieres usar WSL o una maquina virtual, entonces tendríamos una situación grave, porque vas a sufrir muchísimo en todo tu flujo de desarrollo, vas a tener muchísimos bloqueos, vas a perder muchísmo tiempo buscando adaptar las cosas a Windows. Yo te invito a que si eres de este último grupo que no quiere poner ni una maquina virtual o no quiere instalr el WSL, lo reconsideres, porque vas a sufrir muchísimo.

Este curso es bien importante que lo vallas haciendo paso a paso conmigo, también que sigas las instrucciones al pie de la letra.

## Editor de texto: instalando el tuyo
La mayoría de las personas hoy en día están utilizando Visual Studio Code y es el que vamos a estar utilizando en nuestros cursos, así que es el que vamos a instalar.

Visual Studio Code es un Editor de Código free, están construido encima de Open source y se ejecuta y corre en Windows, Linux o Mac. Te sirve para todo tipo de funcionalidades, para Web, para Apps moviles, para Ciencia de Datos y desarrollo de videojuegos, Visual Studio Code es muy versatil y te sirve para programar todo tipo de aplicaciones. Tiene un enfoque modular ya que puedes instalar solo lo que necesites para programar.

Para descargar el instalador haz clic [aquí](https://visualstudio.microsoft.com/es/free-developer-offers/ "aquí"). Elegimos **Visual Studio Code** > Descarga gratuita > Windows x64.

## Extensiones y personalización de Visual Studio Code
Vamos a agregar una serie de extenciones que te van a ayudar muchísimo con todo nuestro código.

1. **Abrimos** Visual Studio Code.
2. Nos dirigimos a **Extensions**.
3. Clik en **Search Extensions in ...**

Las Extenciones a instalr son las siguientes:

- Prettier - Code formatter
- Color Highlight
- Live Server
- Path Intellisense
- Auto Rename Tag
- Material Icon Theme

## ¿Qué es Windows Subsystem for Linux?
Esto es lo que Microsoft biene desarrollando para poder volver a windows 10 una plataforma competitiva para poder desarrollar. Ya que Windows no servía para desarrollo de aplicaciones web. Hoy en día con día con Windows Subsystem for Linux, todo lo puedes hacer desde una terminal de Linux dentro de tu sistema operativo windows. Esto es posible gracias a que microsoft esta desarrollando esta tecnología y esta en su versión 2. Lo que tiene es un nucleo de linux que además, combina tecnologías de virtualización que le permiten ejecutarse super rápido en windows. Con esto te quiero decir que, es de buen rendimiento y es basntante útil.

Si tu no tienes instalado windows 10, primero esfuerzate por tenerlo, vale mucho la pena. Es un gran sistema operativo y se esta volviendo una muy buena herramienta de trabajo para desarrollar.

Para actualizar a WSL 2, debe ejecutar Windows 10.
- Para sistemas x64: versión 1903 o superior, con compilación 18362 o superior.
- Para sistemas ARM64: versión 2004 o superior, con compilación 19041 o superior.
- Las versiones anteriores a 18362 no son compatibles con WSL 2. Utilice el Asistente de actualización de Windows para actualizar su versión de Windows.

Para comprobar la versión de mi windows 10 utilizamos el Ejecutador de tareas y escribimos el comando `winver`. Si tu no tienes esta versión lo que puedes hacer es **Buscar actualizaciones** en windows update.

## Instalación de Windows Subsystem for Linux
Ya podemos instalar WSL. ¡Hagamoslo!

1. Habilite el subsistema de Windows para Linux. Abra PowerShell como administrador (menú Inicio> PowerShell> haga clic con el botón derecho> Ejecutar como administrador) e ingrese este comando:

```shell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
Damos **Enter** y nos aparecerá el siguiente mensaje: `Enabling feature(s)`. Y al final si todo salio bien: `The operation completed successfully`.

2. Habilitar la función de máquina virtual. Abra PowerShell como administrador y ejecute:

````shell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
````

3. Establezca WSL 2 como su versión predeterminada. Abra PowerShell y ejecute este comando para configurar WSL 2 como la versión predeterminada al instalar una nueva distribución de Linux:

````shell
wsl --set-default-version 2
````

Si nos aparece un error **reinicamos la computadora** y listo. Sino funciona deberemos **habilitar la virtualización en la BIOS**.

4. Instale la distribución de Linux que prefiera. Para este caso usaremos **Ubuntu 20.04 LTS**. Desde la **Microsoft Store**.

5. **Abrimos Ubuntu 20.04 LTS**. La primera vez que inicie una distribución de Linux recién instalada, se abrirá una ventana de consola y se le pedirá que espere uno o dos minutos para que los archivos se descompriman y se almacenen en su PC. Debiendo aparecer el mensaje: `Installation successful!`.

***Si le aparece un error*** entonces **Descargue el paquete de actualización del kernel de Linux**:

[https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

Ejecute el paquete de actualización descargado en el paso anterior. (Haga doble clic para ejecutar: se le solicitarán permisos elevados, seleccione "sí" para aprobar esta instalación).

Nuevamente **Establezca WSL 2 como su versión predeterminada**:

````shell
wsl --set-default-version 2
````

Listo! Ahora le deberá aparecer el mensaje: `Installation successful!`. ***Luego, deberá crear una cuenta de usuario y una contraseña para su nueva distribución de Linux.***

**¡FELICIDADES! ¡Ha instalado y configurado con éxito una distribución de Linux que está completamente integrada con su sistema operativo Windows!** para mayor información puede consultar los [Pasos de instalación manual para versiones anteriores de WSL](https://docs.microsoft.com/en-us/windows/wsl/install-manual "Pasos de instalación manual para versiones anteriores de WSL").


## Configuración de Ubuntu en WSL
Una vez creada su nueva distribución de Linux podemos hacer uso de nuestro **conocimiento en Linea de comandos** para crear directorios y movernos entre ellos.

Dentro de nuestro directorio HOME, al cual podemos dirigirnos usando el comando: `cd`, hay que crear nuestro directorio de trabajo. Algo que te tiene que quedar muy claro es que cuando estamos trabajando en WSL 2 para asegurarnos la máxima compatibilidad con todo lo que puedes llegar a trabajar después es super importante que te asegures de que todos tus proyectos están viviendo dentro de Ubuntu, dentro de tu HOME. Así que debermos crear una carpeta aquí la cual será donde vamos a almacenar todos nuestros proyectos que vamos a trabajar.

Para crear el directorio podemos usar el comando: `mkdir <nombre del directorio>`

Si tu le pones **sudo** al inicio de `mkdir`, vas a crear una carpeta pero con permisos de administrador. Siempre que nececites permisos de administrador en algo de tu Ubuntu vamos a utilizar *sudo*.

## Windows Terminal
A continuación te enseñaré cómo usar Ubuntu 20.04 desde Windows Terminal. Para ello:

1. Lo primero que vamos a hacer es **abrir Windows Terminal**. Esto nos abre esta nueva terminal que es super super cool. A mi me gusta porque tiene la características de abrir varias veces nuestra Terminal en una sola ventana. También podemos comfigurarla a nuestro gusto.
2. Hacemos click en la **flechita hacia abajo 🔽**, aun lado de abrir una nueva pestaña. Y nos dirigimos a **Configuración**. Esto nos abrira la ventaja de configuración de Windows Terminal. Aquí deberas elegir como:

- Perfil predeterminado: Ubuntu-20.04
- Iniciar al inicio del equipo: Desactivado
- Modo de inicio: Maximizada
- Comportamiento de una nueva instancia: Dejar el que tiene por defecto
- Tamaño de incio: Dejar el que tiene por defecto

Damos click en Guardar o en Cancelar para recuperar los valores por defecto y !Listo!
Ahora tenemos una Terminal mucho más editable y configurable en colores, en lo que tu quieras lista para trabajar.

## ¿Cómo instalar gestores de paquetes o manejadores de dependencias?
Pasa que Ubuntu y Debian son sistemas operativos basados en Linux, sistemas operativos de Software libre, y estos sistemas operativos utilizan algo llamados gestor de paquetes o manejador de dependencias. Imaginatelo como que son Tiendas como la Microsoft Store, estos gestores de paquetes tienen un repositorio de dependencias, es decir donde almacenan todo lo que tu le puedes instalar a tu Ubuntu. Ahí tu puedes encontrar Software de todo tipo, utilidades de todo tipo para tu sistema y lo tienen registrado en este repositorio de dependencias. Entonces Ubuntu simplemente le dice al repositorio de dependencias ¡Oye hay alguna novedad de todo lo que yo tengo instalado, en el repostorio que necesita actualizar! y sí el repositorio le dice ¡Si, tienes estas novedades actualizalas! tu las puedes actualizar. Esto de que nosotros le preguntemos al repositorio de dependencias si hay cosas nuevas se hace **desde el HOME** con: `apt -get update`. Para hacerlo con permisos de administrador utilizamos el comando: `sudo apt -get update`

Si tu quieres aplicar estas cosas nuevas, tienes que usar el comando: `apt -get upgrade`. Para hacerlo con permisos de administrador utilizamos el comando: `sudo apt -get upgrade`.

Siempre que te detenga la ejecución por algo de `Permision denied`, pon **sudo** 
antes de la instrucción, y eso te ayuda a resolverlo.

Para instalar algo nuevo utilizamos el comando: `sudo apt install <nombre de lo qué quiero instalar>`. Siempre que vallas a instalar algo en tu Ubuntu debes saber para qué lo quieres. Sino no andes instalando cosas que no, eso es regla general en cualquier sistema operativo.

## Instalando Git

No hay un solo desarrollador o desarrolladora que profesional, que pueda decir que se volvio desarrollador o desarrolladora sin saber Git. ¡No existe! Tienes que dominar Git y tienes que dominar GitHub.

Git es el gestor de versiones que nosotros estamos utilizando como el defacto en la industria y GitHub es una plataforma donde todos los equipos van subiendo su código, colaboran entre ellos, entre muchas cosas más.

Si tu quieres borrar un directorio que tiene contendio adentro sin haber inicializado antes un repositorio de Git, utilizamos el comando de borrador recursivo: `rm -rf <nombre del directorio>`. Ubicandonos primero en la carpeta donde esta el directorio que queremos borrar.

Para instalar Git lo primero que hay que hacer es **dirigirnos a nuestro HOME** Y verificar si no ya está instalado en nuestro programa. Para ello utilizamos el comando: `git --version`. En mi caso ya estaba instalado Git en la versión `2.25.1`. En caso de que a ti no te aparezca nada con este comando, para instalar Git utilizamos primero el comando `sudo apt -get update` y luego`sugo apt -get upgrade`, porque siempre es una muy buena práctica que actualices tus paquetes cuando vas a instalar sofware nuevo en tu Ubuntu, es lo correcto. Entonces hecho esto intalamos Git con el comando: `sudo apt install git`. Y damos Enter. En mi caso me dirá que Git ya está instalado.

## Vinculando nuestra llave SSH en GitHub
El curso de Git-y-GitHub-Avanzado disponible en esta cuenta de GitHub, es el que te enseña todo sobre esta herramienta y esta plataforma. Pero igual yo quiero dejarte ya con tu conexión lista desde tu terminal de Ubuntu en Windows hacia GitHub. Así que hagamos eso.

1. Asegurate primero tener una cuenta de GitHub y haber iniciado sesión.
2. Nos dirigimos al HOME usando el comando `cd`.
3. Para crear la llave SSH utilizamos el comando `ssh-keygen -t rsa -b 4096 -C "<tu email en GitHub>"`. El número **4096** indica la complejidad del algoritmo. Y damos **Enter**.
4. Ésto nos dira **generando llave publica y privada**. Y también **nos dira dónde debemos guardar la llave**. Aquí puedes colocar otra carpeta. Pero honestamente no se los recomiendo porque por defecto te la guarda en el HOME. Por eso es importante dirigirnos al HOME antes de crear la llave. La ruta se vería algo así: `(/home/<nombre de usuario>/.ssh/id_rsa>)`. Como podemos observar también me crea una carpeta `.ssh`, la cual es una carpeta oculta. Y un archivo `id_rsa` sin extención. No hagas nada simplemente da un **Enter**.
5. Y listo. Te indica que tu tu identificación ha sido guardada en: `/home/<nombre de usuario>/.ssh/id_rsa>`. Te indica que tu llave pública ha sido guardada en `/home/<nombre de usuario>/.ssh/id_rsa.pub>`. Y te genera un **fingerprint** y un **randomart image**. Estas son maneras de cofirmar que tu llave es de verdad.

No es suficiente con lo que hicimos. El procedimiento es el mismo en Windows y Linux, pero en Mac no. Porque una vez tienes tu llave la tienes que agregar al entorno. Es decir, que el sistema operativo donde tu trabajas sepa que la llave existe. En Windows o Linux:

1. Tienes que revisar que el servido de llaves SSH este prendido. Para ello utilizamos el comando `eval $(ssh-agent -s)`. Al ejecutarlo te tiene que salir algo así: `Agent pid <numero>`. El `<numero>` indica que el proceso está corriendo. Entonces todo está bien.
2. El siguiente paso es agregar la llave a nuestro sistema, decirle que existe. Para ello tenemos que recordar donde la creamos: `(/home/<nombre de usuario>/.ssh/id_rsa>)` es decir en el HOME. Para dirigirnos ahí usamos el comando `cd`.
3. Una vez en el HOME utilizamos el comando `ssh-add ~/.ssh/id_rsa`. Nos muestara las dos llaves:` id-rsa` y `id-rsa.pub`. Debo agregar la llave privada la que no tiene extensión. Así que volvemos a ejecutar el comando `ssh-add ~/.ssh/id_rsa`. Y listo. Se nos mostrará el siguiente mensaje: `Identity added: <ruta de la llave en el home> (<correo electronico>)`.

## Inicializar un repositorio de Git y traer los archivos de mi repositorio en GitHub

Ahora ya podemos inicializar un repositorio de Git y traer los archivos de mi repositorio en GitHub. Para ello:

1. Creamos un directorio de trabajo.
2. Dentro del directorio que acabamos de crear inicializamos Git con el comando `git init`.
3. Cambiamos la configuración del nombre de usuario en Git  con el comando: `git config --global user.name "<nombre de usuario>"` y cambiamos la configuración del email en Git con el comando: `git config --global user.email "<correo electrónico>"`.
4. Agregamos un origen remoto, debiendo comprobar que estamos el directorio o repositorio correcto. Para agregarlo utilizamos el comando: `git remote add origin <dirección del respositorio remoto en GitHub>`. Para agregar la `<dirección del respositorio remoto en GitHub>` utilizamos la pestaña **Code** en GitHub donde nos da la opción de ***Clone*** por **HTTPS** O **SSH**. Copiamos la URL elegida al comando `git remote` y damos **Enter**. Lo que ocurre es que se agrega un origen remoto al cual podemos hacer **fetch** y **push**.
5. Para visualizar esta información utilizamos el comando `git remote -v`. Mostrando además la URL elegida para el origen remoto.
6. Listo ahora podemos hacer un `git pull origin master` para traernos todos los archivos que están en mi repositorio en GitHub.



