# Tutorial de Branch

## Crear un nuevo repositorio y un commit initial: init, add, commit

Primero, crea un nuevo directorio y crea un repositorio vacío en él. Aquí, hemos creado un directorio llamado `tutorial_branch`.
Seguiremos utilizando este directorio en tutoriales posteriores.
```
$ mkdir ~/tutorial_branch
$ cd ~/tutorial_branch
$ git init
Initialized empty Git repository
in /Users/yourname/Desktop/tutorial/.git/
```

Cree un achivo de texto llamado myfile.txt en el directorio tutorial_branch.
En el contenido del archivo, introduzca el siguiente texto.
```
Comandos Git para manejar branch
```

Haga un commit initial.
```
$ git add myfile.txt
$ git commit -m "first commit"
[master (root-commit) a73ae49] first commit 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 myfile.txt
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9ae26d44-1aee-47fe-89f2-d9bc3cf7eb51)

## Crear un branch: branch

Aquí, creamos una rama llamada `issue1`.

Los branches pueden crearse con el comando `branch`.
```
$ git branch <branchname>
```

Vamos a crear un branch llamada `issue1`.
```
$ git branch issue1
```

Si ejecuta el comando `branch` sin ningún argumento, podrá ver una lista de branch. El branch con el prefijo * es el branch actual.
```
$ git branch
  issue1
* master
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/df3abd5a-832f-4dd5-82cd-6bff5d8e289e)

## Cambiar el branch actual: checkout

Para añadir _commits_ a su branch `issue1` recién creada, necesita cambiar el branch actual a `issue1`.

El cambio de branch se realiza con el comando `checkout`.
```
$ git checkout <branch>
```

Cambie a el branch `issue1`.
```
$ git checkout issue1
Switched to branch 'issue1'
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8b882d05-93a6-42ab-9ce5-43e0e5a2d517)

___
#### CONSEJOS
Ejecute el comando `checkout` con la opción `-b` para crear y cambiar de branch a la vez.
```
$ git checkout -b <branch>
```
___
Si ejecutas commit mientras el branch actual es `issue1`, el historial se registrará en `issue1`.<br>
Añade una descripción del comando `checkout` a `myfile.txt` y luego ejecuta commit.
```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
```
```
$ git add myfile.txt
$ git commit -m "Se ha añadido la descripción de la Checkout"
[issue1 b2b23c4] Se ha añadido la descripción de la Checkout
 1 files changed, 1 insertions(+), 0 deletions(-)
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/96da7a3b-c2af-49cb-a30b-6ee122e332dc)

## Integrar Branches y Funcionalidades: merge

Fusiona los cambios realizados en la rama `issue1` con la rama `master`. Las ramas se fusionan utilizando el comando `merge`.
```
$ git merge <branch>
```

Este comando fusiona el branch del parámetro en el branch apuntado por _HEAD_.<br>
Para meter `issue1` en `master`, primero ve a `master`.

```
$ git checkout master
Switched to branch 'master'
```

Antes de ejecutar `merge`, abra `myfile.txt` una vez para comprobar el contenido.
```
Comandos Git para manejar branch
```

El archivo se editó en `issue1`, por lo que el contenido de `myfile.txt` en `master` no se ha modificado.
```
$ git merge issue1
Updating 1257027..b2b23c4
Fast-forward
 myfile.txt |    1 +
 1 files changed, 1 insertions(+), 0 deletions(-)
```

La confirmación apuntada por `master` se ha movido a la misma posición que `issue1`.
Esta `merge` es un `fast-forward (avance rápido) merge`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/5b0349aa-a39f-489d-b601-b5a1708cfeab)

Abra `myfile.txt` para ver el contenido.<br>
Los cambios se reflejan en el archivo.
```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
```

Compruebe el historial de cambios del repositorio usando la comando `git log`.<br>
Se ha añadido commit de "Se ha añadido la descripción de la Checkout".

