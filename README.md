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

## PASO 2.5 (Mezcla)

Como hemos creado dos ramas ahora vamos a querer mezclarlas. Cómo nuestra rama principal va a ser  main primero debemos situarnos en ella y utilizar estos comandos.

```bash
git checkout main
git merge <rama> # Esto hará que se mezcle la rama en la que estamos actualmente con la que hemos seleccionado en el comando.
```
Después de esto se nos genera un commit automático de merge que querremos subir con un *git push* al repositorio remoto para que esté actualizado.

Hay varias estrategias para poder mezclar ramas:

- Merge.
- Merge con squash.
- Fast-forward merge.

Cada una de ellas tiene sus diferencias y utilizaremos la que más nos convenga.


# PASO 3

En el caso de que queramos eliminar información de los commit de la rama en la qu estamos trabajando podemos utilizar el siguiente comando

```bash
git reset --hard HEAD
```

Esto provoca que se nos reinicie todo el espacio de trabajo incluso lo que estaba en staging excepto los ficheros que están en untracked.

# PASO 4

En el paso 4 vamos a ver los posibles conflictos de merge que pueden ocurrir al trabajar con varias ramas que están actualizando las mismas líneas del mismo fichero.
El problema lo hemos podido arreglar eligiendo que cambios queríamos para la rama main y la rama fix-readme, además luego hemos añadido el contenido del paso 4 (este mismo).

Se pueden ver los commits de ambas ramas en el repositorio junto a sus fast-forward merge.

# PASO 5

En el caso de que queramos trabajar de manera colaborativa es muy importante este comando:

```bash
git pull
```

Además en el caso de que queramos hacer una nueva feature de nuestro software debemos crear una nueva rama y al hacer push se crea lo que se llama **pull-request**. Esto consiste
en una petición de hacer merge a main para poder revisar los cambios nuevos que vamos a implementar. Esto nos ayuda a poder comprobar que los cambios que vamos a añadir
están bien integrados.