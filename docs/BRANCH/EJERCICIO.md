# EJERCICIO

Resuelva las preguntas 1-9 utilizando los comandos en GitBash.<br>
Para las preguntas 5~8, por favor ilustre el historial de commit en el siguiente archivo.

[BRANCH_EJERCICIO_ilustración_de_commit](https://docs.google.com/spreadsheets/d/1763DsBZPt-7kl0fg1HtroLk920xyLFV6MMoJdqzck2k/edit?usp=sharing)

## Pregunta 1

Cree una carpeta `~/ejercicio2` y colócala bajo control Git.

## Pregunta 2

En el directorio `~/ejercicio2`, cree un archivo llamado `resumen_de_branch.txt` y haga commit.<br>
En el contenido del archivo, introduzca el siguiente texto.
Compruebe el historia de commit.
```
Resumen de branch
```

## Pregunta 3

Crea un branch `add_description_of_type_of_branch` y un branch `add_description_of_command` y muévale a el branch `add_description_of_type_of_branch`.<br>
Luego muestre la lista de branches.

## Pregunta 4

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.
```
Base Branch (Rama Base):
  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
Topic Branch (Rama de Tema):
  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.
```

## Pregunta 5

Ve a el branch llamado `add_description_of_command`.<br>
Luego muestre la lista de branches.

## Pregunta 6

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.

```
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

## Pregunta 7

Fusiona los cambios realizados en `add_description_of_type_of_branch` en el `master`.<br>
Ve a `master` y luego importa `add_description_of_type_of_branch` usando comando `merge`.

## Pregunta 8

Fusiona los cambios realizados en `add_description_of_command` en el `master`.

Importa la `add_description_of_command` usando comando `merge` también.<br>
En caso de conflicto, modifique el contenido del archivo para que los cambios realizados en ambas branches permanezcan.

## Pregunta 9

Elimine `add_description_of_type_of_branch` y `add_description_of_command`.<br>
Luego muestre la lista de branches.

## Solucion

```

koyno@LAPTOP-J1K1E58T MINGW64 ~
$ mkdir ~/ejercicio2

koyno@LAPTOP-J1K1E58T MINGW64 ~
$ cd ~/ejercicio2

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2
$ git init
Initialized empty Git repository in C:/Users/koyno/ecicio2/.git/

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ nano resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git add resumen_de_branch.txt
warning: LF will be replaced by CRLF in resumen_de_branch.txt.
The file will have its original line endings in your working directory

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   resumen_de_branch.txt


koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git commit -m "primer commit"
[master (root-commit) abc450a] primer commit
 1 file changed, 1 insertion(+)
 create mode 100644 resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git log
commit abc450a4a3a1a41122d6dc718822a0755f61c9be (HEAD -> master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:38:51 2024 -0600

    primer commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git brach add_description_of_type_of_branch
git: 'brach' is not a git command. See 'git --help'.

The most similar command is
        branch

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch add_description_of_type_of_branch

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch add_description_of_command

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git checkout add_description_of_type_of_branch
Switched to branch 'add_description_of_type_of_branch'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git branch
  add_description_of_command
* add_description_of_type_of_branch
  master

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ nano resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git diff
warning: LF will be replaced by CRLF in resumen_de_branch.txt.
The file will have its original line endings in your working directory
diff --git a/resumen_de_branch.txt b/resumen_de_branch.txt
index e15e94f..1379294 100644
--- a/resumen_de_branch.txt
+++ b/resumen_de_branch.txt
@@ -1 +1,5 @@
 Resumen de branch
+Base Branch (Rama Base):
+  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
+Topic Branch (Rama de Tema):
+  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git add resumen_de_branch.txt
warning: LF will be replaced by CRLF in resumen_de_branch.txt.
The file will have its original line endings in your working directory

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git status
On branch add_description_of_type_of_branch
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   resumen_de_branch.txt


koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git commit -m "He añadido descripciones del tipo de branch"
[add_description_of_type_of_branch bba6438] He añadido descripciones del tipo de branch
 1 file changed, 4 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git log
commit bba64383319d773a2d03d88ad3a09178a97a573b (HEAD -> add_description_of_type_of_branch)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:43:13 2024 -0600

    He añadido descripciones del tipo de branch

commit abc450a4a3a1a41122d6dc718822a0755f61c9be (master, add_description_of_command)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:38:51 2024 -0600

    primer commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_type_of_branch)
$ git checkout add_description_of_command
Switched to branch 'add_description_of_command'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git branch
* add_description_of_command
  add_description_of_type_of_branch
  master

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ nano resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git diff
diff --git a/resumen_de_branch.txt b/resumen_de_branch.txt
index e15e94f..508a424 100644
--- a/resumen_de_branch.txt
+++ b/resumen_de_branch.txt
@@ -1 +1,4 @@
 Resumen de branch
+Checkout: Cambia o Crea Branch
+Branch: Crear, eliminar branch o ver una lista de branch
+Merge: Integrar branch

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git add resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git commit -m "He añadido descripciones de comandos"
[add_description_of_command 23aadd7] He añadido descripciones de comandos
 1 file changed, 3 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git log
commit 23aadd776bd1d4791bd34e1023082e9dc11f9367 (HEAD -> add_description_of_command)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:45:44 2024 -0600

    He añadido descripciones de comandos

commit abc450a4a3a1a41122d6dc718822a0755f61c9be (master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:38:51 2024 -0600

    primer commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (add_description_of_command)
$ git checkout master
Switched to branch 'master'

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch
  add_description_of_command
  add_description_of_type_of_branch
* master

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git merge add_description_of_type_of_branch
Updating abc450a..bba6438
Fast-forward
 resumen_de_branch.txt | 4 ++++
 1 file changed, 4 insertions(+)

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git merge add_description_of_command
Auto-merging resumen_de_branch.txt
CONFLICT (content): Merge conflict in resumen_de_branch.txt
Automatic merge failed; fix conflicts and then commit the result.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master|MERGING)
$ nano resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master|MERGING)
$ git add resumen_de_branch.txt

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master|MERGING)
$ git commit -m "Fusionar branch descripcion de commando"
[master 641501c] Fusionar branch descripcion de commando

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git log
commit 641501cfd0d90e5dfdabb87650563fee12146108 (HEAD -> master)
Merge: bba6438 23aadd7
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:50:04 2024 -0600

    Fusionar branch descripcion de commando

commit 23aadd776bd1d4791bd34e1023082e9dc11f9367 (add_description_of_command)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:45:44 2024 -0600

    He añadido descripciones de comandos

commit bba64383319d773a2d03d88ad3a09178a97a573b (add_description_of_type_of_branch)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:43:13 2024 -0600

    He añadido descripciones del tipo de branch

commit abc450a4a3a1a41122d6dc718822a0755f61c9be
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Thu May 16 10:38:51 2024 -0600

    primer commit

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch -d git branch -d
error: branch 'git' not found.
error: branch 'branch' not found.

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch -d add_description_of_type_of_branch add_description_of_command
Deleted branch add_description_of_type_of_branch (was bba6438).
Deleted branch add_description_of_command (was 23aadd7).

koyno@LAPTOP-J1K1E58T MINGW64 ~/ejercicio2 (master)
$ git branch
* master
```
