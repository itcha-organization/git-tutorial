# Ejercicios de pull request

## Pregunta 1

Cree una carpeta `~/ejercicio4` y colócala bajo control Git.<br>
En el directorio `~/ejercicio4`, cree un archivo llamado `pull_request.txt`, introduzca el siguiente texto y guárdelo. 
```
Resume de PULL REQUEST
```
Luego ejecte un commit y compruebe el historia de commit.

## Pregunta 2

Ve a GitHub en su navegador y cree un repositorio privado, llamado `ejercicio4`.

## Pregunta 3

Registre el repositorio remoto `ejercicio4` creado en la pregunta 2 como remoto del repositorio local `ejercicio4` usando comandos en GitBash.<br>
A continuación, realice un push para reflejar los cambios en el repositorio remoto.<br>
Luego, compruebe que el historial de commits y el archivo se han añadido en GitHub.

## Pregunta 4

Crea un branch `add_description_of_type_of_branch` y un branch `add_description_of_command` y muévale a el branch `add_description_of_type_of_branch`.<br>
Luego muestre la lista de branches.

## Pregunta 5

Añada el siguiente texto a `pull_request.txt` y ejecute commit.<br>
Ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio4`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.
```
Base Branch (Rama Base):
  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
Topic Branch (Rama de Tema):
  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.
```

## Pregunta 6

En GitHub, crea un pull request y fusiona los cambios de Pregunta 5 en el branch master.

## Pregunta 7

Ve a el branch llamado `add_description_of_command`.<br>
Añada el siguiente texto a `pull_request.txt` y ejecute commit.<br>
Ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio4`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.

```
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

## Pregunta 8

En GitHub, crea un pull request para fusiona los cambios de Pregunta 7 en el branch master.

## Pregunta 9

Los pull requests creados en Pregunta 8 no pueden fusionarse debido a un conflicto.<br>
Por favor, resuelva el conflicto y fusione el pull request.<br>
Esta vez, modifique el contenido del archivo para que los cambios realizados en ambas branches permanezcan cuando resuelva el conflicto.

___
### Consejos de pregunta 9
En primer lugar, en el branch en el que está trabajando, ejecuta un pull hacia el branch destino de la pull request.<br>
De este modo, los últimos cambios en el branch de destino de la pull request se incorporan a el branch de trabajo.

En segundo lugar, modifique el contenido del archivo para resolver el conflicto.

En tercer lugar, ejecute commit y push cuando la modificación se haya completado.
___


### Ejemplo de solución
```
koyno@LAPTOP-J1K1E58T MINGW64 ~
$ mkdir ~/ejercicio4

koyno@LAPTOP-J1K1E58T MINGW64 ~
$ cd ~/ejercicio4

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4
$ git init
Initialized empty Git repository in C:/Users/koyno/ejercicio4/.git/

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ nano pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git add pull_request.txt
warning: LF will be replaced by CRLF in pull_request.txt.
The file will have its original line endings in your working directory

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git commit -m "first commit"
[master (root-commit) 02b8579] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git log
commit 02b85798f907451050063751f4a3ebc24f9a3479 (HEAD -> master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:57:04 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git remote add origin git@github.com:kkk-commit/ejercicio4.git

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git remote -v
origin  git@github.com:kkk-commit/ejercicio4.git (fetch)
origin  git@github.com:kkk-commit/ejercicio4.git (push)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 246 bytes | 82.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/ejercicio4.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git branch add_description_of_type_of_branch

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git branch add_description_of_command

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (master)
$ git checkout add_description_of_type_of_branch
Switched to branch 'add_description_of_type_of_branch'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git branch
  add_description_of_command
* add_description_of_type_of_branch
  master

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ nano pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git diff
warning: LF will be replaced by CRLF in pull_request.txt.
The file will have its original line endings in your working directory
diff --git a/pull_request.txt b/pull_request.txt
index bf3b9ad..d5f1808 100644
--- a/pull_request.txt
+++ b/pull_request.txt
@@ -1 +1,5 @@
 Resume de PULL REQUEST
+Base Branch (Rama Base):
+  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
+Topic Branch (Rama de Tema):
+  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git add pull_request.txt
warning: LF will be replaced by CRLF in pull_request.txt.
The file will have its original line endings in your working directory

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git status
On branch add_description_of_type_of_branch
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git commit -m "He añadido descripciones del tipo de branch"
[add_description_of_type_of_branch 422cf04] He añadido descripciones del tipo de branch
 1 file changed, 4 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git push origin -u add_description_of_type_of_branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 563 bytes | 187.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'add_description_of_type_of_branch' on GitHub by visiting:
remote:      https://github.com/kkk-commit/ejercicio4/pull/new/add_description_of_type_of_branch
remote:
To github.com:kkk-commit/ejercicio4.git
 * [new branch]      add_description_of_type_of_branch -> add_description_of_type_of_branch
Branch 'add_description_of_type_of_branch' set up to track remote branch 'add_description_of_type_of_branch' from 'origin'.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_type_of_branch)
$ git checkout add_description_of_command
Switched to branch 'add_description_of_command'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ nano pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git diff
diff --git a/pull_request.txt b/pull_request.txt
index bf3b9ad..e3ff416 100644
--- a/pull_request.txt
+++ b/pull_request.txt
@@ -1 +1,4 @@
 Resume de PULL REQUEST
+Checkout: Cambia o Crea Branch
+Branch: Crear, eliminar branch o ver una lista de branch
+Merge: Integrar branch

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git add pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git status
On branch add_description_of_command
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git commit -m "He añadido descripciones de comandos"
[add_description_of_command 29450dd] He añadido descripciones de comandos
 1 file changed, 3 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git log
commit 29450dd26ebf3779a61b5a41b2feb6f32d9ce2be (HEAD -> add_description_of_command)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 16:11:24 2024 -0600

    He añadido descripciones de comandos

commit 02b85798f907451050063751f4a3ebc24f9a3479 (origin/master, master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:57:04 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git push origin -u add_description_of_command
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 384 bytes | 192.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'add_description_of_command' on GitHub by visiting:
remote:      https://github.com/kkk-commit/ejercicio4/pull/new/add_description_of_command
remote:
To github.com:kkk-commit/ejercicio4.git
 * [new branch]      add_description_of_command -> add_description_of_command
Branch 'add_description_of_command' set up to track remote branch 'add_description_of_command' from 'origin'.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git pull origin master
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 936 bytes | 133.00 KiB/s, done.
From github.com:kkk-commit/ejercicio4
 * branch            master     -> FETCH_HEAD
   02b8579..7d9c43b  master     -> origin/master
Auto-merging pull_request.txt
CONFLICT (content): Merge conflict in pull_request.txt
Automatic merge failed; fix conflicts and then commit the result.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ git status
On branch add_description_of_command
Your branch is up to date with 'origin/add_description_of_command'.

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   pull_request.txt

no changes added to commit (use "git add" and/or "git commit -a")

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ nano pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ git diff
diff --cc pull_request.txt
index e3ff416,d5f1808..0000000
--- a/pull_request.txt
+++ b/pull_request.txt
@@@ -1,4 -1,5 +1,8 @@@
  Resume de PULL REQUEST
 +Checkout: Cambia o Crea Branch
 +Branch: Crear, eliminar branch o ver una lista de branch
 +Merge: Integrar branch
+ Base Branch (Rama Base):
+   Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
+ Topic Branch (Rama de Tema):
+   Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ git add pull_request.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ git status
On branch add_description_of_command
Your branch is up to date with 'origin/add_description_of_command'.

All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   pull_request.txt


koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command|MERGING)
$ git commit -m "Resolución de conflictos."
[add_description_of_command 6535b0f] Resolución de conflictos.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git log
commit 6535b0fa8888218ce170d9a00eb6013bae902b64 (HEAD -> add_description_of_command)
Merge: 29450dd 7d9c43b
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 16:21:52 2024 -0600

    Resolución de conflictos.

commit 29450dd26ebf3779a61b5a41b2feb6f32d9ce2be (origin/add_description_of_command)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 16:11:24 2024 -0600

    He añadido descripciones de comandos

commit 7d9c43b31706fbaabf804dda2e49342a8b8df848 (origin/master)
Merge: 02b8579 422cf04
Author: kkk-commit <83223664+kkk-commit@users.noreply.github.com>
Date:   Thu May 23 07:09:31 2024 +0900

    Merge pull request #1 from kkk-commit/add_description_of_type_of_branch

    He añadido descripciones del tipo de branch

commit 422cf0410595f64a8531f6f831481f67a0796419 (origin/add_description_of_type_of_branch, add_description_of_type_of_branch)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 16:03:50 2024 -0600

    He añadido descripciones del tipo de branch

commit 02b85798f907451050063751f4a3ebc24f9a3479 (master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Wed May 22 15:57:04 2024 -0600

    first commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio4 (add_description_of_command)
$ git push origin -u add_description_of_command
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 428 bytes | 214.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:kkk-commit/ejercicio4.git
   29450dd..6535b0f  add_description_of_command -> add_description_of_command
Branch 'add_description_of_command' set up to track remote branch 'add_description_of_command' from 'origin'.
```
