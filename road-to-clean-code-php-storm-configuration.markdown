Configurando PhpStorm
=====================

Configuración de *PhpStorm* para facilitar el cumplimiento de los estándares *PSR* y los *Symfony Coding Standards* **con el objetivo de mejorar la calidad del código**

*PHP Code Sniffer*
-----------------------------
Una vez instalado podemos integrarlo con nuestro *IDE* para facilitar y asegurar un mayor uso.

#### Indicamos emplazamiento del ejecutable:

1. En `File->Settings` nos dirigimos a la sección `Languages & Frameworks -> PHP -> Code Sniffer` y hacemos click en el botón `[...]` de configuración.
2. Seleccionamos el ejecutable o le indicamos el *path*: `/urs/local/bin/phpcs` si hemos seguido las instrucciones anteriores.

#### Configuramos las alertas:
1. Nos dirigimos a `File -> Settings -> Editor -> Inspections`.
2. En el listado buscaremos *PHP* y seleccionaremos y habilitaremos `PHP Code Sniffer validation`.
3. Hacemos click en el botón de *atualizar* que aparece en la sección derecha junto a `Coding standard:` y seleccionamos `Symfony` de entre las opciones.

### Reformatear usando los *Symfony Coding Standards*

Podemos configurar *PhpStorm* para que use la guia de estilos de **Symfony** cada vez que usemos el reformateado que nos ofrece (`Ctrl+Alt+L` por defecto).
Dicha guía de estilos sigue a su vez la *PSR-1* y la *PSR-2*.

1. En la sección `File -> Settings -> Editor -> Code Style -> PHP`  localizamos el botón `Set from...` situado en la esquina superior derecha.
2.  Hacemos click y seleccionamos la opción `Symfony2` dentro de `Predefined Style`.

*PHP Mess Detector*
--------------------

1. Nos dirigimos a `File -> Settings -> Languages & Frameworks -> PHP -> Mess Detector` y clickamos sobre el icono `[...]` para establecer una nueva configuración.
2. Establecemos el *path* (`/usr/local/bin/phpmd`), el máximo de mensajes por fichero (20 por ejemplo) y el *timeout* que le damos para que el proceso conteste (10 o 15s es lo recomendable).
3. Ahora debemos habilitarlo en `File -> Settings -> Editor -> Inspections` en `PHP -> PHP Mess Detector validation`
4. Se le puede especificar una ruta con un fichero de configuración, tanto a la orden de linea de comandos como a *PhpStorm* en esta sección.

** Puede ser neceario un reinicio de PhpStorm para funcionar correctamente.

Si se quiere hacer una configuración más granulada se puede visitar la documentación oficial. ¡Cualquier propues es bienvenida!
