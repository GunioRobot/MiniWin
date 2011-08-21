
Instalación
===========

Antes que nada: `descarga MiniWin <https://github.com/pauek/MiniWin/zipball/master>`_.

Verás que dentro del Zip hay dos ficheros: ``miniwin.h`` y
``miniwin.cpp``. Puedes ignorar todo lo demás. Estos dos ficheros
deben formar parte del proyecto que se está desarrollando. En C++, se
pueden hacer programas con más de un fichero fuente (si estás
empezando esto no es evidente). Entornos de programación como `Dev-C++
<http://www.bloodshed.net/devcpp.html>`_, `Code::Blocks
<http://www.codeblocks.org>`_ o `Geany <http://www.geany.org>`_
permiten compilar este tipo de proyectos.

Compilación con MiniWin en Dev-C++
----------------------------------

Para crear proyectos usando MiniWin en Dev-C++, simplemente crea un proyecto
dentro de un directorio (pongamos que se llama "MiJuego"), y haz lo
siguiente:

- Copia los ficheros ``miniwin.h`` y ``miniwin.cpp`` en el directorio
  "Mi Juego".

- Añade al proyecto de Dev-C++ el fichero ``miniwin.cpp``. Esto se
  puede hacer clicando con el botón derecho el proyecto y luego
  seleccionando "Añadir al proyecto".

- Haz el programa principal (la función ``main``) en un fichero aparte
  (por ejemplo: ``mijuego.cpp``), y lo añades también al proyecto
  (tendrás, entonces, 2 ficheros en el proyecto, el tuyo y
  ``miniwin.cpp``).

- En el fichero ``mijuego.cpp`` añades las líneas::

     #include "miniwin.h"
     using namespace miniwin;

  al principio de todo, tal como pones normalmente otros
  ``#include``\s o el ``using namespace std``.

Ahora puedes compilar el proyecto.

Compilar con MiniWin en Geany
-----------------------------

Para crear un proyecto que use MiniWin en Geany hay que seguir los
siguientes pasos:

- Crea un directorio (por ejemplo "MiJuego").

- Copia los ficheros ``miniwin.h`` y ``miniwin.cpp`` al directorio
  "Mi Juego".

- Haz el programa principal (la función ``main``) en un fichero aparte
  (por ejemplo: ``mijuego.cpp``), y lo añades también al proyecto
  (tendrás, entonces, 2 ficheros en el proyecto, el tuyo y
  ``miniwin.cpp``).

- Crea un fichero ``Makefile`` en el directorio "MiJuego" (con Geany
  mismo) y escribes lo siguiente (puedes sustituir ``mijuego`` por el nombre
  que hayas escogido)::

     all: mijuego

     mijuego: miniwin.o mijuego.o
        g++ -o mijuego.exe miniwin.o mijuego.o -mwindows

Ahora, para compilar el proyecto, debes seleccionar la opción del menú
"Construir" que pone "Compilar", pero la que aparece justo al lado de
"Mayúsc + F9" (o apretar esa tecla). Mira la ventana de mensajes para
comprobar que todo sale bien