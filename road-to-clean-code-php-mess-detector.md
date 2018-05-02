PHP Mess Detector
=================

¿Qué es?
--------
Es una herramienta que arroja métricas de nuestro código. Desde que una función tiene demasiados argumentos, hasta que nuestro código no es el más eficiente o tiene demasiada anidación, pasando por parámetros no usados o clases demasiado largas.

Instalación
-----------

1. Lo instalaremos de forma **global** utilizando *composer*.

  ```
  composer global require "phpmd/phpmd"
  ```

2. Si queremos utilizarlo fácilmente desde consola podemos hacer un *soft link* en `/usr/local/bin`.

  ```
  $ ln -s ~/.composer/vendor/bin/phpmd /usr/local/bin/phpmd
  ```

3.  Ejemplo de ejecución:

  ```
  phpmd ./src/ text cleancode,codesize,controversial,design,naming,unusedcode > ../mess_detector.log`
  ```
