# Ejercicios de compartir repositorios

Resuelva las preguntas 1-9 utilizando GitHub y los comandos en GitBash.<br>
**Para las preguntas 5~9, por favor ilustre el historial de commit y estado de repositorio en el siguiente archivo.**

[COMPARTIR_REPOSITORIOS_EJERCICIO_ilustración_de_commit](https://docs.google.com/spreadsheets/d/17ZizmqThkzv2ltMsF9tek2KEg70L7MoMWexVv4-gEzY/edit?usp=sharing)

## Pregunta 1

Cree una carpeta `~/ejercicio3` y colócala bajo control Git.<br>
En el directorio `~/ejercicio3`, cree un archivo llamado `compartir_repositorios.txt`, introduzca el siguiente texto y guárdelo. 
```
Resume de compartir repositorios
```
Luego ejecte un commit y compruebe el historia de commit.

## Pregunta 2

Ve a GitHub en su navegador y cree un repositorio privado, llamado `ejercicio3`.

## Pregunta 3

Registre el repositorio remoto `ejercicio3` creado en la pregunta 2 como remoto del repositorio local `ejercicio3` usando comandos en GitBash.<br>
A continuación, realice un push para reflejar los cambios en el repositorio remoto.<br>
Luego, compruebe que el historial de commits y el archivo se han añadido en GitHub.

## Pregunta 4

Clone el repositorio remoto `ejercicio3` y cree un repositorio local `ejercicio3-clone`.<br>
Luego vaya al directorio `ejercicio3-clone` y compruebe el historia de commit y el archivo en el repositorio local `ejercicio3-clone`.

## Pregunta 5

Añade el siguiente texto a `compartir_repositorios.txt` y ejecuta commit en `ejercicio3-clone`. Luego compruebe el historia de commit.

```
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
Remote add: puede nombrar y registrar la dirección del repositorio remoto para no tener que introducir una larga dirección de repositorio remoto cada vez
```

## Pregunta 6

En `ejercicio3-clone`, ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio3`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.

## Pregunta 7

Primero, vaya al directorio `~/ejercicio3` y compruebe el historial de commits y el contenido del archivo.<br>
A continuación, obtenga los últimos cambios del repositorio remoto en el repositorio local `ejercicio3` usando pull.<br>
Luego, compruebe el historial de commits y el contenido del archivo de nuevo.

## Pregunta 8

En el repositorio local `ejercicio3`, cree un branch `añadir_descripción_de_origin` y ve a el branch.<br>
Añade el siguiente descripción de `origin` al final del `compartir_repositorios.txt` y ejecute commit.

```
origin: Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado origin
```

## Pregunta 9

En el repositorio local `ejercicio3`, ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio3`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.

## Ejemplo de solución
```

koyno@LAPTOP-J1K1E58T MINGW64 ~
$ mkdir ~/ejercicio3

koyno@LAPTOP-J1K1E58T MINGW64 ~
$ cd ~/ejercicio3

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3
$ git init
Initialized empty Git repository in C:/Users/koyno/ejercicio3/.git/

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ nano compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git add compartir_repositorios.txt
warning: LF will be replaced by CRLF in compartir_repositorios.txt.
The file will have its original line endings in your working directory

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   compartir_repositorios.txt


koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git commit -m "first commit"
[master (root-commit) 8071e8c] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git log
commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f (HEAD -> master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git remote add origin git@github.com:kkk-commit/ejercicio3.git

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git remote -v
origin  git@github.com:kkk-commit/ejercicio3.git (fetch)
origin  git@github.com:kkk-commit/ejercicio3.git (push)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 266 bytes | 88.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/ejercicio3.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git clone git@github.com:kkk-commit/ejercicio3.git ~/ejercicio3-clone
Cloning into 'C:/Users/koyno/ejercicio3-clone'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ cd ~/ejercicio3-clone

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git log
commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f (HEAD -> master, origin/master, origin/HEAD)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ cat compartir_repositorios.txt
Resume de compartir repositorios

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ nano compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git diff
diff --git a/compartir_repositorios.txt b/compartir_repositorios.txt
index 6a99620..756eee5 100644
--- a/compartir_repositorios.txt
+++ b/compartir_repositorios.txt
@@ -1 +1,5 @@
 Resume de compartir repositorios
+Push: sube su historial de cambios al repositorio remoto
+Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
+Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
+Remote add: puede nombrar y registrar la dirección del repositorio remoto para no tener que introducir una larga dirección de repositorio remoto cada vez

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git add compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git commit -m "He añadido descripciones del comando"
[master 75e437f] He añadido descripciones del comando
 1 file changed, 4 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git log
commit 75e437fe36f5c6c7b8a79233d578d49846d40c7f (HEAD -> master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:12:36 2024 -0600

    He añadido descripciones del comando

commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f (origin/master, origin/HEAD)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ git push -u origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 502 bytes | 167.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/ejercicio3.git
   8071e8c..75e437f  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3-clone (master)
$ cd ~/ejercicio3

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git log
commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f (HEAD -> master, origin/master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ cat compartir_repositorios.txt
Resume de compartir repositorios

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 482 bytes | 20.00 KiB/s, done.
From github.com:kkk-commit/ejercicio3
 * branch            master     -> FETCH_HEAD
   8071e8c..75e437f  master     -> origin/master
Updating 8071e8c..75e437f
Fast-forward
 compartir_repositorios.txt | 4 ++++
 1 file changed, 4 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git log
commit 75e437fe36f5c6c7b8a79233d578d49846d40c7f (HEAD -> master, origin/master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:12:36 2024 -0600

    He añadido descripciones del comando

commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ cat compartir_repositorios.txt
Resume de compartir repositorios
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
Remote add: puede nombrar y registrar la dirección del repositorio remoto para no tener que introducir una larga dirección de repositorio remoto cada vez

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (master)
$ git checkout -b añadir_descripción_de_origin
Switched to a new branch 'añadir_descripción_de_origin'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ nano compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git diff
diff --git a/compartir_repositorios.txt b/compartir_repositorios.txt
index 756eee5..e91a7da 100644
--- a/compartir_repositorios.txt
+++ b/compartir_repositorios.txt
@@ -3,3 +3,4 @@ Push: sube su historial de cambios al repositorio remoto
 Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
 Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
 Remote add: puede nombrar y registrar la dirección del repositorio remoto para no tener que introducir una larga dirección de repositorio remoto cada vez
+origin: Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado origin

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git add compartir_repositorios.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git status
On branch añadir_descripción_de_origin
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   compartir_repositorios.txt


koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git commit -m "He añadido descripciones del origin"
[añadir_descripción_de_origin bc59fa4] He añadido descripciones del origin
 1 file changed, 1 insertion(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git log
commit bc59fa4220ca90ab0857ca63dd1399d393a68302 (HEAD -> añadir_descripción_de_origin)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:29:25 2024 -0600

    He añadido descripciones del origin

commit 75e437fe36f5c6c7b8a79233d578d49846d40c7f (origin/master, master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:12:36 2024 -0600

    He añadido descripciones del comando

commit 8071e8c12f64256fa5aaeb028df26f9e09a50e0f
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:06:34 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio3 (añadir_descripción_de_origin)
$ git push origin añadir_descripción_de_origin
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 427 bytes | 213.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'añadir_descripción_de_origin' on GitHub by visiting:
remote:      https://github.com/kkk-commit/ejercicio3/pull/new/a%C3%B1adir_descripci%C3%B3n_de_origin
remote:
To github.com:kkk-commit/ejercicio3.git
 * [new branch]      añadir_descripción_de_origin -> añadir_descripción_de_origin

```
