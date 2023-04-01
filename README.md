# Maestría en Ciencia de Datos - Ejercicio 1.

## Ejercicio de Docker con imagen MySQL:

### Objetivo

Descargar la imagen oficial de MySQL, ejecutar un contenedor, y probar los comandos básicos de Docker.

### Pre requisitos.

1. Accede a GitHub y asegúrate de haber iniciado sesión en tu cuenta. 
2. Ve al repositorio [https://github.com/ucb-software/mcd-ejercicio-1](https://github.com/ucb-software/mcd-ejercicio-1) .
3. Haz clic en el botón "Code" en la parte superior derecha del repositorio.
4. Selecciona "Open with Codespaces" en el menú desplegable.
5. En la siguiente página, haz clic en el botón "New codespace".
6. Se abrirá una ventana de Visual Studio Code en tu navegador. Aquí puedes trabajar en el proyecto como lo harías en tu propio equipo.

¡Eso es todo! Ahora puedes comenzar a trabajar en el repositorio mcd-ejercicio-1 con tu entorno Codespace de GitHub.


### Instrucciones.

A continuación se detallan los pasos para el ejercicio.

Paso 1: Descargar la imagen oficial de MySQL.

```bash

docker pull mysql:latest
```

Verificar que imágenes tienen instaladas

```bash

docker images
```

Paso 2: Ejecutar un contenedor MySQL utilizando los comandos y opciones requeridos.

```bash

docker run --name my-mysql -p 3306:3306 -v my-mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:latest
```

Explicación: 
- `--name my-mysql`: Asigna el nombre "my-mysql" al contenedor. 
- `-p 3306:3306`: Mapea el puerto 3306 del host al puerto 3306 del contenedor. 
- `-v my-mysql-data:/var/lib/mysql`: Monta el volumen "my-mysql-data" en la ruta "/var/lib/mysql" del contenedor. 
- `-e MYSQL_ROOT_PASSWORD=123456`: Establece la variable de entorno "MYSQL_ROOT_PASSWORD" con el valor "my-secret-pw". 
- `-d`: Ejecuta el contenedor en modo "detached" (desacoplado).


Paso 3: Verificar que el contenedor esté en ejecución.

```bash

docker ps
```



Paso 4: Detener el contenedor MySQL.

```bash

docker stop my-mysql
```



Paso 5: Iniciar el contenedor MySQL nuevamente.

```bash

docker start my-mysql
```



Paso 6: Verificar nuevamente que el contenedor esté en ejecución.

```bash

docker ps
```



Paso 7: Eliminar el contenedor MySQL.

```bash

docker rm -f my-mysql
```



Paso 8: Verificar que el contenedor haya sido eliminado. Aqui el atributo -a me muestra contenedores que esten o no, en ejecución.

```bash

docker ps -a
```



Al completar este ejercicio, habrás practicado cómo descargar imágenes de Docker, ejecutar contenedores, y utilizar comandos básicos de Docker con las opciones `-p`, `-v`, y `-e`.
