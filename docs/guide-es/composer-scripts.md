Comandos de Composer
===================

Yii2 ROA Application usa los comandos de composer para facilitar el proceso de
instalación y manejar operaciones recurrentes.

Eventos de Composer
-------------------

Lista de eventos de composer implementados para esta aplicación
[Read more](https://getcomposer.org/doc/articles/scripts.md#event-names)

### pre-install-cmd

Revisa que la versión de composer sea `1.3` o superior.

### pre-update-cmd

Revisa que la versión de composer sea `1.3` o superior.

### command

Revisa que la versión de composer sea `1.3` o superior.

Comandos Personalizados
-----------------------

Lista de los comandos creados para esta aplicación.

### deploy

`composer deploy -- [arguments]`

Ejecuta todas las operaciones necesarias para tener una aplicación funcional.

* Nota: Requiere tener instalado el framework de Yii2.

> Usa los comandos
>
> * `update --prefer-stable --prefer-dist`
> * [deploy-framework](#deploy-framework)
> * [deploy-database](#deploy-database)
> * [run-tests](#run-tests)

Parametro |	Tipo   | Descripción                    | Valor por Defecto
--------- | ------ | ------------------------------ | -------
env       | string | Ambiente de trabajo            | dev
overwrite | bool   | Sobreescribir archivos locales | Preguntar
dbhost    | string | Host de la Base de Datos       | Preguntar[127.0.0.1]
dbuser    | string | Usuario de la Base de Datos    | Preguntar[root]
dbpass    | string | contraseña de la Base de Datos | Preguntar
dbname    | string | Nombre de la Base de Datos     | Preguntar[yii2_app_roa]

### deploy-framework

`composer deploy-framework -- [arguments]`

Crea los archivos de configuración local, asigna permisos a carpetas y crea
enlaces simbolicos. Este comando reemplaza el comando `init` del repositorio
[yii2-app-avanced].

Puede ser personalizado editando la clase `console\FrameworkListener`.

* Nota: Requiere tener instalado el framework de Yii2.

Parámetro |	Tipo   | Descripción                    | Valor por Defecto
--------- | ------ | ------------------------------ | -------
env       | string | Ambiente de trabajo            | dev
overwrite | bool   | Sobreescribir archivos locales | Preguntar

### deploy-database

`composer deploy-database -- [arguments]`

Asegura la existencia de la base de datos y carga la estructura usando migraciones y fixtures.

> Nota: De momento sólo `mysql` esta soportado.

* Nota: Requiere tener instalado el framework de Yii2.

> Usa los commandos
>
> * [config-database](#config-database)
> * [run-migrations](#run-migrations)
> * [run-fixtures](#run-fixtures)
> * [clear-cache](#clear-cache)

Parámetro |	Tipo   | Descripción      | Valor por defecto
--------- | ------ | ---------------- | ---------
dbhost    | string | Host de BD       | Preguntar[127.0.0.1]
dbuser    | string | Usuario de BD    | Preguntar[root]
dbpass    | string | Contraseña de BD | Preguntar
dbname    | string | Nombre de BD     | Preguntar[yii2_app_roa]

### truncate-database

`composer truncate-database`

Elimina la base de datos configurada y la crea de nuevo usando migrations y
fixtures.

> Nota: De momento sólo `mysql` esta soportado.

> Nota: requiere tener una base de datos configurada.

> Usa los commandos
>
> * [run-migrations](#run-migrations)
> * [run-fixtures](#run-fixtures)
> * [clear-cache](#clear-cache)

### config-database

`composer config-database -- [arguments]`

Asegura los permisos de la base de datos y los guarda para uso del framework.

Puede personalizarse editando la clase `console\DatabaseListener`.

* Nota: De momento sólo `mysql` esta soportado.

* Nota: Requiere tener instalado el framework de Yii2.

Parámetro |	Tipo   | Descripción      | Valor por defecto
--------- | ------ | ---------------- | ---------
dbhost    | string | Host de BD       | Preguntar[127.0.0.1]
dbuser    | string | Usuario de BD    | Preguntar[root]
dbpass    | string | Contraseña de BD | Preguntar
dbname    | string | Nombre de BD     | Preguntar[yii2_app_roa]

### run-migrations

`composer run-migrations`

Corre las migraciones necesarias para la aplicación.

Se personaliza editando el archivo `composer.json`.

* Nota: Soporta todos los drivers de Yii2 luego de configuración.

* Nota: Requiere tener instalado el framework de Yii2.

### run-fixtures

`composer run-fixtures`

Corre todos los fixtures que cargan la información básica de la BD.

Se personaliza editando el archivo `composer.json`.

* Nota: Soporta todos los drivers de Yii2 luego de configuración.

* Nota: Requiere tener instalado el framework de Yii2.

### clear-framework-cache

`composer clear-framework-cache`

Limpia toda la cache del framework.

Se personaliza editando el archivo `composer.json`.

### run-tests

`composer run-tests`

Atajo para correr las pruebas de Codeception.

Se personaliza editando el archivo `composer.json`.

### run-coverage

`composer run-coverage`

Atajo para correr las pruebas de Codeception con cobertura de código.

Se personaliza editando el archivo `composer.json`.
