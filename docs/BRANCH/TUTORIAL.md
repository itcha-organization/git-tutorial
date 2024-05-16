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

Cree un achivo de texto llamado `myfile.txt` en el directorio tutorial_branch.

```
$ nano myfile.txt
```

En el contenido del archivo, introduzca el siguiente texto.

```
Comandos Git para manejar branch
```

Haga un commit initial.
```
$ git add myfile.txt
$ git status
$ git commit -m "first commit"
$ git log
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9ae26d44-1aee-47fe-89f2-d9bc3cf7eb51)

## Crear un branch: branch

Aquí, creamos un branch llamada `issue1`.

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

Cambie a el branch `issue1`.<br>
A continuación, utilice el comando `git branch` para confirmar que el branch actual ha pasado al `issue1`.
```
$ git checkout issue1
Switched to branch 'issue1'
$ git branch
* issue1
  master
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
$ nano myfile.txt
$ git diff
$ git add myfile.txt
$ git status
$ git commit -m "Se ha añadido la descripción de la Checkout"
$ git log
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/96da7a3b-c2af-49cb-a30b-6ee122e332dc)

## Integrar Branches y Funcionalidades: merge

Fusiona los cambios realizados en el branch `issue1` con el branch `master`. Los branches se fusionan utilizando el comando `merge`.
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
El archivo se editó en `issue1`, por lo que el contenido de `myfile.txt` en `master` no se ha modificado.
```
$ cat myfile.txt
Comandos Git para manejar branch
```

Antes de ejecutar `merge`, compruebe el historial de cambios del repositorio usando la comando `git log`.El historial contiene solo initial commit.
```
$ git log
```

Ejecte `merge`.
```
$ git merge issue1
```

El commit apuntado por `master` se ha movido a la misma posición que `issue1`.
Esta `merge` es un `fast-forward (avance rápido) merge`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/f262c0c9-089c-4dcd-9f98-a47fa7f472ff)

Abra `myfile.txt` para ver el contenido.<br>
Los cambios se reflejan en el archivo.
```
$ cat myfile.txt
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
```

Compruebe el historial de cambios del repositorio usando la comando `git log`.<br>
Se ha añadido commit de "Se ha añadido la descripción de la Checkout".
```
$ git log
```

## Eliminar branch: branch -d

El contenido de `issue1` se ha fusionado con éxito en `master` y debería eliminarse.

Para eliminar un branch, ejecute el comando `branch` con la opción `-d`.
```
$ git branch -d <branchname>
```

Para eliminar `issue1`, emita el siguiente comando.

```
$ git branch -d issue1
Deleted branch issue1 (was b2b23c4).
```

Ahora `issue1` ha sido eliminado. Utilice el comando `branch` para ver si el branch ha sido eliminada.
```
$ git branch
* master
```

La historia en este punto se parece a esto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c5b6fc59-ba23-4ee7-9bdb-a9128661706e)

## Trabajar en paralelo usando branches

A continuación, cree dos branches y trabaje en paralelo.

Primero, crea `issue2` y `issue3` y muévele a `issue2`.

```
$ git branch issue2
$ git branch issue3
$ git checkout issue2
Switched to branch 'issue2'
$ git branch
* issue2
  issue3
  master
```
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9bc95e2c-359e-4833-a747-944fe55b7d4d)

Añade una descripción del comando `branch` a `myfile.txt` en `issue2` y ejecuta commit.

```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
```
```
$ nano myfile.txt
$ git diff
$ git add myfile.txt
$ git status
$ git commit -m "Se ha añadido la descripción de Branch"
$ git log
```
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/55b30951-61be-4df9-9d1d-4191e4b45d7f)

Luego pasa al `issue3`.

```
$ git checkout issue3
Switched to branch 'issue3'
```

Abra `myfile.txt`. La adición de la descripción del comando `branch` se hizo en `issue2`, por lo que el `myfile.txt` en `issue3` sólo tiene la descripción del comando `checkout`.

Ahora vamos a añadir una descripción del comando `merge` y ejecutar commit.

```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
Merge: Integrar branch
```
```
$ nano myfile.txt
$ git diff
$ git add myfile.txt
$ git status
$ git commit -m "Se ha añadido la descripción de Merge"
$ git log
```
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/794fee99-66d8-44ad-8075-9d476f6c8b5c)

El trabajo para añadir la descripción de `branch` y la descripción de `merge` podría realizarse por separado.

## Resolución de conflictos en el merge

Fusiona los cambios realizados en `issue2` y los cambios realizados en `issue3` en el `master`.

Primero, ve a `master` y luego importa `issue2`.
```
$ git checkout master
Switched to branch 'master'
$ git merge issue2
Updating b2b23c4..8f7aa27
Fast-forward
 myfile.txt |    2 ++
 1 files changed, 2 insertions(+), 0 deletions(-)
```

Esta `merge` es un `fast-forward (avance rápido) merge`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c8c04bc3-16de-4214-8141-3aa910b76580)

A continuación, importa la `edición3`.

```
$ git merge issue3
Auto-merging myfile.txt
CONFLICT (content): Merge conflict in myfile.txt
Automatic merge failed; fix conflicts and then commit the result.
```

El `merge` automática ha fallado. Parece que se ha producido un conflicto porque se ha cambiado el contenido de la misma línea. El contenido de `myfile.txt` en este momento tendría este aspecto.

```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
<<<<<<< HEAD
Branch: Crear, eliminar branch o ver una lista de branch
=======
Merge: Integrar branch
>>>>>>> issue3
```

En caso de conflicto, debe corregirse manualmente al código correcto.<br>
Esta vez, tanto la descripción de Branch como la de Merge deben mantenerse, así que modifíquelas como sigue.<br>
Para el desarrollo real, es mejor consultar con el equipo cómo corregir el problema correctamente.

```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

Ahora que el conflicto se ha corregido, ejecute `commit` de nuevo.

```
$ nano myfile.txt
$ git status
$ git add myfile.txt
$ git commit -m "Fusionar branch issue3"
# On branch master
nothing to commit (working directory clean)
$ git log
```

La historia es la siguiente.<br>
Esta _merge_ soluciona un conflicto, por lo que se ha creado un nuevo _merge commit_ para registrar el cambio. La cabecera de `master` se ha movido allí.<br>
Un _merge_ de este tipo se denomina _non fast-forward merge_.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e1e25920-bd2b-4929-a6cc-c16bde0570d1)

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/5564ac5f-18db-42b4-91a7-78bd108ae75a)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2f4547f5-a5d4-4e4d-abad-0b42ef1475db)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac5f20a5-4132-4fe6-be7d-8f6618aa1753)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2b638f26-24ec-49e2-bd7c-c55dec4d7bf5)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/894669d7-985b-42af-b979-5f9c268814d0)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6db1b549-8f89-414e-937c-1e8d38af5035)
