# Pruebas

Este repositorio como dice su descripción sirve para poder hacer pruebas con git y aprender como funciona.
A lo largo de este README se podrán ver los pasos que se han ido siguiendo por si alguien quiere replicarlo
y aprender.

# PASO 0

Debemos de haber creado el repositorio vacío con o sin licencia dependiendo de que queramos. Hay una web que
nos puede ayudar a elegir la licencia correcta. [Web](https://choosealicense.com/).

# PASO 1

Crear README.md dentro del repositorio con: 

```bash
touch README.md
```
Antes de hacerlo debemos asegurarnos que estamos en el directorio de trabajo con la carpeta .git del repositorio.
Después lo modificaremos con nuestro editor de texto de preferencia y vamos a hacer el primer commit y push.

```bash
git status #Esto nos muestra el estado del repositorio y los archivos modificados
git add . #Añade todos los cambios mostrados en git status pero si quisieramos solo añadir uno debemos poner el nombre del fichero visto en git status
git commit -m "README.md added" #Nos hace el commit con el título (por eso la opcion -m) que queramos ponerle
git push origin main #Este comando nos sube el repositorio en el estado de nuestro repositorio local al remoto y lo fusiona a la vez.
# Esto último lo hace en la rama main (veremos las ramas y su gestión más adelante)
```

Podemos ver la lista de commits con el comando siguiente:

```bash
git log # Nos va a mostrar todos los commits realizados hasta este momento en el repositorio con su autor y hash
```

# PASO 2 (RAMAS)

En este paso vamos a ver cómo podemos crear nuevas ramas en nuestro repositorio y cómo gestionarlas.

Comandos importantes para trabajar con ramas:

```bash
git branch featrue1 # Sirve para crear una nueva rama
git branch --list # Nos muestra por pantalla las ramas creadas en nuestro repositorio
git branch -d <rama> # Elimina una rama
git checkout <rama> # Nos sirve apra cambiar el HEAD (puntero de la rama en la que estamos trabajando) para trabajar en la rama que queremos
git checkout -b <rama> # Esto hace lo mismo que el comando anterior pero creándonos la rama
```
Vamos a crear una rama llamada documentation que tenga una carpeta llamada docs y dentro dos archivos llamados index.html y styless.css

Una vez hecho eso vamos a cambiar a la rama main y modificar el README.md (como estoy haciendo ahora)

Cuando hemos terminado estos pasos si vemos el log en forma de grafo con el comando siguiente:

```bash
git log --graph --all --oneline
```
Podemos ver las ramas que tenemos en nuestro repositorio.

Vamos a volver a la rama documentation y vamos a añadir un par de commits más.
