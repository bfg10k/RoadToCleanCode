PHP Coding Standards Fixer
==========================

¿Qué es?
--------
No es más que otra herramienta que nos ayuda a que nuestro código siga los estándares que hayamos definido.

Instalación
-----------

1. Lo instalaremos de forma **global** utilizando *composer* (podríamos instalarlo a nivel de proyecto, con curl...).

  ```
  composer global require "friendsofphp/php-cs-fixer"
  ```

2. Lo *linkamos* en `/usr/local/bin` para facilitar su uso:

  ```
  $ ln -s ~/.composer/vendor/bin/php-cs-fixer /usr/local/bin/php-cs-fixer
  ```

3. Para utilizarlo simplemente hemos de ejecutar el comando de la siguente forma:

  ```
  php-cs-fixer fix /path/al/directorio/o_fichero --rules=@Symfony,-@PSR1,-blank_line_before_return,strict_comparison
  ```

4. Para hacer el uso más comodo se puede definir un fichero de configuración (en cada proyecto) para cumplir diferentes normas según el
   proyecto, el fichero de configuración debe llamarse `.php_cs.dist`

5. Siempre puede usarse con la opción `--dry-run` y solo mostrará los ficheros que deberían ser modificados sin realizar los cambios.

#### Propuesta de fichero `.php_cs.dist` (debe devolver una instancia de `\PhpCsFixer\Config`):

    ```
    <?php

    $finder = PhpCsFixer\Finder::create()
        ->notPath('vendor')
        ->exclude('node_modules')
        ->exclude('tests')
        ->exclude('node_modules')
        ->exclude('web')
        ->exclude('docs')
        ->exclude('docker')
        ->exclude('bin')
        ->in(__DIR__);

    return PhpCsFixer\Config::create()
        ->setRules(
            [
                '@PSR2' => true,
                '@Symfony' => true,
                'array_syntax' => ['syntax' => 'short'],
                'is_null' => true, //risky, puede provocar comportamientos extraños si is_null ha sido sobrescrita
                'linebreak_after_opening_tag' => true,
                'mb_str_functions' => true,
                'protected_to_private' => false,
                'psr4' => true, //risky, cambia el nombre de la clase para que coincida con el nombre del fichero
            ]
        )
        ->setFinder($finder)
        ->setCacheFile(__DIR__.'var/php_cs_cache/.php_cs.cache');

    ```

Para que esta propuesta funcione hay que añadir la opción `--alow-risky` a la hora de ejecutar `php-cs-fixer`.
