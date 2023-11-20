# maraAGVDimpl1
Mara ETL implementation of project one in spanish for educational purposes in Big Data Analytics.

## Iniciemos...

[Descargar Ubuntu Destop 22.04.3 LTS x64](https://releases.ubuntu.com/jammy/)

[Descargar VBox reciente 7.0.12](https://download.virtualbox.org/virtualbox/7.0.12/VirtualBox-7.0.12-159484-Win.exe)

[Descargar el Oracle VM Vbox Extension Pack 7.0.12](https://download.virtualbox.org/virtualbox/7.0.12/Oracle_VM_VirtualBox_Extension_Pack-7.0.12.vbox-extpack)

Instala VBox.
Ubica tu ISO de UDLTS22.
Instala el Extension Pack con doble click al archivo.

###Instalando en VBox
- Nueva
- Crear máquina virtual en modo experto...
Para propósitos educativos, configuración sugerida...

- Nombre: Ubuntu22Mara
- Imagen ISO: Buscar el iso de ubuntu 22 descargado.
- Marcar la casilla omitir instalacion desatendida
- En hardware:
 - En RAM: 4096MB si es pobible, si no, 3072MB, si no, 2048MB, si no, 1024MB
 - En núcleos de CPU: 2 si es posible.
 - En disco duro: 50GB si es posible.
- **Terminar**

Dar click derecho a la maquina Ubuntu22Mara y picar en configuración:
- Ir a pantalla.
 - En memoria de video poner 64MB si es posible, si no, 32MB.
- Ir a Carpetas compartidas.
 - Damos clic al boton de la carpeta azul con símbolo +.
 - En ruta de carpeta, seleccionamos otro y por lo general nos abre un explorador en la carpeta de usuario de nuestro Windows, ahí creamos una nueva carpeta que se llame "Compartido", y la seleccionamos en "[Seleccionar carpeta]".
 - En punto de montaje dejamos vacío por el momento.
 - Marcamos la casilla "Automontar".
 - Aceptar. Aceptar.

### Arranca la máquina y se inicia el instalador...

Cuando arranque vas a ver el GRUB

- Ahí donde está Try or Install Ubuntu dale enter, o si lo dejas sin hacer nada va proceder con la opcion remarcada en blanco.

- Vamos a ver el fonfo de pantalla de Jammy Jellyfish y aparecerá el instalador de Ubuntu Desktop 22 LTS.
 - Dejenlo en inglés y ponen Install Ubuntu.
 - En Keyboard layout, deben elegir su idioma que tiene su teclado para que las teclas escriban lo esperado...
 - ...Usualmente es Spanish (Latin American), pero.
 - ...Si tu teclado tiene las llaves y los corchetes estan en otras teclas arriba, es un teclado Spanish.
 - ...Si tu teclado no tiene letra ñ, es un teclado English.
 - ...Elige sabiamente. Una vez elijas dale continue.
 - En Updates,
 - Dejen Normal,
 - Marquen palomita en Download Updates...
 - Y denle continue.
 - En partitions dejen "Erase disk..." y denle a Install Now y continue.
 - En Where are you.
 - -Pongan New York. NO PONGAN New York Time. Tampoco Cancún.
 - En Who are you?
 - - En name: Alumno
 - **ATENCION** No hagan caso y borren las weas que pone automáticamente.
 - - En Computer's name: ubuntu22mara
 - - En Pick username: datos
 - - En password: 12345
 - - En confirm: 12345
 - - Marquen Login Automatically.
 - Denle a continuar
 - Ahora va a estar instalando un rato. unos 5 minutos dependiendo de los recurso de la maquina virtual.
 - Cuando termine aceptar la opcion de reiniciar.
 - VBox va a expulsar el ISO.
 - Cuando ubuntu pregunte presionar enter, le ponen enter.
 - Se reinicia y ya estaria listo para empezar lo demás.

## Ya tenemos Ubuntu.
- Cuanto termine de iniciar deberia entrar directo al usuario datos.
- La ventana de inicio de ubuntu mandenla a ... cerrar.
- En un momento saldrá software updater a pedir un intall now, aceptenlo y pongan la contraseña.
- En lo mientras abran una terminal y agreguenla a favoritos.}
- Cuando Software Updater lo pida, reincien ahora.
 
### Instalar la imagen de CD de los complementos de invitado.
- Es util hacer esto.
- En la barra de menus de nuestra ventana de máquina virtual veremos el menú "Dispositivos".
- En dicho menú vamos a seleccionar la opción "Instalar la imagen de CD de los complementos de invitado".
- En la barra lateral de ubuntu veremos un pequeño CD sobre la papelera de ubuntu, la seleccionamos.
- En la parte superior leeremos "VBOX_GAs..." y hay un boton con tres puntos a la derecha, le damos click y seleccionamos "Open in terminal".
- En la terminal abierta le ponemos: 
- ```./autorun.sh```
- Comenzará a instalar los módulos y se tardará un rato.
- Notaremos que nuestra ventana de máquina virtual cambia o se mueve, es normal.
- Cuando termine le apachurran 'enter' 
- En la barra de menus de nuestra ventana de máquina virtual veremos el menú "Dispositivos".
- En portapapales compartido pongan la opcion: Bidireccional
- Otra cosa, si redimensionan la ventana de su maquina virtual esta ya podrá va a ajustar la resolución acorde al tamaño, intenten redimensionar a un tamaño que permita trabajar con comodidad
- debemos apagar la máquina virtual.

### Poniendo a punto nuestra instalación de ubuntu.
- Ahora es como un coche recien salido de una agencia y nos sirve para hacer bien una cosa, transportarnos.
- Pero necesitamos darle mantenimiento y añadirle caracteristicas antes de implementar todo lo que necesita mara ETL.
- Vamos a actualizar todo lo que podamos y a instalar los paquetes que necesitemos.
- AVISO: Estos comandos al ser interactivos llegan a solicitar confirmación, estar pendiente.
- Encender la máquina virtual y abrir una terminal
- sudo apt update
- sudo apt upgrade
- sudo apt install curl

---
## Ahora sí viene lo chido
En este apartado vamos apoyarnos en las guías del Dr. Martin Loeztch, Jan Katins y Christian Stade-Schuldt, además de guias de proyectos de código de terceros como Git, Homebrew, PostgreSQL, entre otros

###Proyecto Mara, lightweight data warehousing in Python.
- [https://github.com/mara](https://github.com/mara)

 - [Proyecto de ejemplo 1](https://github.com/mara/mara-example-project-1)
 
 - [Proyecto de ejemplo 2](https://github.com/mara/mara-example-project-2)
 
# NO INSTALEN Homebrew
# REPITO, NO INSTALEN Homebrew.
 
### Vamos a tratar de ir en orden usando el proyecto 1.
- Ejecutar comando:
- sudo apt install git dialog coreutils graphviz python3 python3-dev python3-venv
- Cuando pida confirmación, le apachurran al a tecla 'Y'.

### Instalar PosgreSQL 12 - APT no EOL.
Vamos a instalar PostgreSQL 12 desde el repositorio APT!
Recordemos que nuestro target es un sistema Linux en Ubuntu 22.04 Jammy, ya no hay soporte APT para ubuntu inferior al 20. Sin embargo pudieramos makear del source, pero podemos evitarnos la fatiga.
- Metan esta sarta de comandos en la terminal.
- **$** ```sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'```
- **$** ```wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -```
- **$** ```sudo apt-get update```
- **ATENCION**, queremos sí o sí un PostgreSQL versión 12, por favor, si el sistema está limpio, asegurarnos que estamos solicitando la instalación de PostgreSQL-12, de lo contrario es probable que tengamos que purgar el sistema de cualquier conexion con variables de entorno de instalaciones de postgresql no compatibles con mara.
- **$** ```sudo apt-get -y install postgresql-12```
- **$** ```sudo apt-get install postgresql-server-dev-12```

- Intalar esto:
- sudo apt-get install gcc
- sudo apt-get install build-essential

Recordartorio solamente, este comando permite entrar al usuario postgres para la terminal, por ahora no se requiere.
- sudo -i -u postgres


### Instalar CStore_fdw.
- abrimos la terminal y creamos un directorio llamado git, nos movemos ahí y vamos a clonar repos uno por uno.
- ```mkdir git```
- ```cd git```
- ```git clone https://github.com/citusdata/cstore_fdw.git```
- ```git clone https://github.com/citusdata/postgresql-hll.git```
- ```git clone https://github.com/mara/mara-example-project-1.git```

- Intalar esto:
- ``` apt-get install protobuf-c-compiler```
- ```sudo apt-get install libprotobuf-c-dev```

- Poner nuestro psql en path listo para makear.
- ```cd cstore_fdw/```
- ```PATH=/usr/lib/postgresql/12/bin/:$PATH make```
- ```sudo PATH=/usr/lib/postgresql/12/bin/:$PATH make install```

- Pondremos a CStore en el .conf de postgres
- - ```sudo nano /etc/postgresql/12/main/postgresql.conf```
- - Buscamos la linea que diga:
- - > **#**shared_preload_libraries = ''  # (change requires restart)
- - La editamos tal que diga:
- - shared_preload_libraries = 'cstore_fdw'  # (change requires restart)
- - Lo que hemos hecho es decomentar el parametro y agregar el valor cstore_fdw.
- - Guardamos y salimos con control+O, enter y control+X

### Instalar HLL.
- - Vamos al repo clonado de HLL:
- - ```cd ~/git/postgresql-hll/```
- - ```make```
- - ```sudo make install```
- - ```sudo -i -u postgres```
- - ```psql```
- - ```CREATE EXTENSION hll;```
- - ```quit```
- - ```exit```

### Creando roles de PostgreSQL-12
Lamentablemente no es pan ni de canela, queremos tener un usuario muy poderoso con acceso a postgres:
- sudo -u postgres psql postgres
- CREATE ROLE datos SUPERUSER LOGIN
- CREATE ROLE root SUPERUSER LOGIN
- para salirnos necesitamos poner \q, que se lee diagonal invertida y la q, y enter.

### Adaptando el .Conf de postgresql-12
- - ```sudo -i```
 - - - ```12345```
 - - - ```chown 777 /media/sf_Compartido/```
 - - - ```exit```

- -
