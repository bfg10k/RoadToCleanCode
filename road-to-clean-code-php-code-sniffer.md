PHP Code Sniffer
==============

¿Qué es?
--------
Un Code Sniffer se encarga de, una vez configuradas una serie de reglas, detectar en el código posibles violaciones de estas. Además *PHPCS* viene con una herramienta para corregir parte de estas violaciones *automágicamente*.

Instalación
-----------

1. Lo instalaremos de forma **global** utilizando *composer* (podríamos instalarlo a nivel de proyecto, con curl...).
 
  ```
  composer global require "squizlabs/php_codesniffer=*"
  ```

  El *CodeSniffer* se instalará en el directorio global de composer, y estará disponible en `~/.composer/vendor/bin` (este es el directorio por defecto, puede comprobarse con `composer global config bin-dir --absolute`) (C:\Users\%username%\AppData\Roaming\Composer/vendor/bin en Windows).

2. Si queremos utilizarlo fácilmente desde consola podemos hacer un *soft link* en `/usr/local/bin`.

  ```
  $ ln -s ~/.composer/vendor/bin/phpcs /usr/local/bin/phpcs
  ```

3.  Ejecutando `phpcs -i` veremos la lista de estándares de código instalados.
  
  ```
  $ phpcs -i

  The installed coding standards are Zend, PHPCS, PSR2, Squiz, PEAR, PSR1 and MySource
  ```

Configurando el estándar de *Symfony*
------------------------------------
1. Instalar el estándar.

  ```
  $ composer global require "escapestudios/symfony2-coding-standard=*"
  ```

2. Configurar el estándar para *PHPCS*.

  ```
  phpcs --config-set installed_paths ~/.composer/vendor/escapestudios/symfony2-coding-standard
  ```

3. Si ejecutamos `phpcs -i` debería aparecer el nuevo estándar.
4. Por defecto usa el estándar de *PEAR*, para utilizar el de *Symfony* debemos ejecutar `phpcs --config-set default_standard Symfony`.

Utilizando *PHPCS*
----------------
1. Ejecutamos el comando sobre la carpeta del código que queremos probar:

  ```
  $ phpcs /path/to/code
  ```

2. Devolverá un informe y un resumen de errores. También nos dirá cuantos es capaz de solucionar de forma automática.

3. Solucionando problemas de forma automática con la herramienta `phpcbf` de *PHPCS*:

  ```
  $ phpcbf /path/to/code
  ```

Configuración opcional
----------------------

1. `summary report format` por defecto:

  ```
  $ phpcs --config-set report_format summary
  ```

2. Mostrar progreso por defecto

  ```
  $ phpcs --config-set show_progress 1
  ```

3. Usando colores

  ```
  $ phpcs --config-set colors 1
  ```