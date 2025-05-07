# Ejercicio: Experimentar el GitHub Flow en equipo
- Actividades por grupo (3 - 5 integrantes)
- Cree un repositorio en GitHub y comparta el perfil de cada miembro con el equipo.

## Objetivo
Fortalecer el uso de Git y GitHub para el trabajo colaborativo en equipo incluyendo: creación del repositorio, clonación, trabajo en ramas, Pull Request

## Preparación Previa: Creación del repositorio remote (Responsable: Integrante 1)
- Inicie sesión en GitHub y cree un repositorio privado llamado `proyecto-presentacion-perfil`.
- En la página del repositorio que ha creado, haga clic en `Invitar colaboradores` para invitar a los miembros del equipo.
  > ![image](https://github.com/user-attachments/assets/9fa242c9-32cd-41f4-acc1-5a905bcf559e)
- En local, crear un directorio llamado `proyecto-presentacion-perfil`
- Ingresar al directorio
- Inicializar repositorio Git
- Crear un archivo `README.md`
- Crear el primer commit con la descripción “Configuración inicial”
- Enlazar con el repositorio remote de GitHub que acaba de crear
- Subir el primer commit al repositorio remote

## Tarea1: Crear un perfil y fusionarlo en la rama remota `main`
Siga las siguientes instrucciones para crear un archivo de perfil y subirlo al repositorio remoto.

### PASO1: Clonar un repositorio remoto de GitHub (Excepto Integrante 1)
Utilice el comando `clone` para clonar un repositorio. `<repositorio>` es la URL del repositorio remoto y `<directorio>` es el nombre del directorio a clonar.
> ```
> $ git clone <repositorio> <directorio>
> ```
Ejemplo:
> ![image](https://github.com/user-attachments/assets/6aaa708a-0c95-4900-9efc-db8f4a270566)

Ejecute los siguientes comando para ir al repositorio local clonado y compruebe el historial de _commit_.
```
cd ~/proyecto-presentacion-perfil
```
```
git log
```

### PASO2: Crear un branch para una tarea
Para empezar a trabajar, cree un branch del tema con el nombre `perfil-"su nombre"` y muévase a ese branch.
> ![image](https://github.com/user-attachments/assets/1649cd37-ab9b-4c4a-a30e-c8597144e7b8)

> [!NOTE]
>  Normalmente, el nombre de un branch es un resumen de la tarea separado por guiones,
> <br>por ejemplo `funcion-login`,`ui-modo-oscuro`.

> [!CAUTION]
>  Se desaconseja el uso de la `ñ` o de `caracteres acentuados(á, é, í, ó, ú)` en los nombres de branch.

### PASO3&4: Crear un archivo de perfil en y ejecutar commit.
Cree un archivo llamado `Perfil_"su nombre".md`, escribe su cumpleaños y guarde el archivo.
> ![image](https://github.com/user-attachments/assets/927179e2-48e6-4db2-ba16-a072da9cce58)
> ![image](https://github.com/user-attachments/assets/814c58db-29be-4745-9737-198d28193f17)

> [!NOTE]
>  `.md` es un archivo en formato Markdown, un tipo de lenguaje que puede convertir texto plano escrito en notación simple en HTML y otros formatos.

Cree un commit y guarda los cambios en el repositorio local.
> ![image](https://github.com/user-attachments/assets/3da79e72-217b-45dd-976a-dc6cd5b05dd9)

### PASO5 Subir el cambio al repositorio remoto con `push`.
Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
`<repositorio>` especifica el repositorio remoto al que hacer push y `<refspec>` el branch a el que hacer push.
```
$ git push <repositorio> <refspec>...
```
Ejemplo:
> ![image](https://github.com/user-attachments/assets/52f0f5bf-9f62-462b-89a5-52d9962a77b7)

Abra el repositorio remoto de GitHub en su navegador y compruebe que se ha añadido el branch que ha subido.
> ![image](https://github.com/user-attachments/assets/0a299244-c40b-42d7-8459-d875defc0667)

### PASO6 Crear ***Pull Request***
Vamos a crear un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.

Haga clic en `Compare & pull request`
> ![image](https://github.com/user-attachments/assets/0ad9089b-e7ef-4986-ac50-dfeedc71019f)

Asegúrese de que _base_(el branch de destino) es el branch `main` y _compare_(el branch de origen) es el branch que subió.
<br>
Después, Haga clic en `Create pull request`
> ![image](https://github.com/user-attachments/assets/40980a6f-d43f-4dd9-878a-f63626b5aa1e)

La siguiente imagen muestra el `Pull Request` creada.
> ![image](https://github.com/user-attachments/assets/7b8624d8-7c86-4d27-a3b1-3dbffd856648)

### PASO7: Fusionar ***Pull Request***
Haga clic en `Merge pull request`.
Después, Haga clic en `Confirm merge`.
> ![image](https://github.com/user-attachments/assets/ddcc7013-f1c5-4de2-b1e3-971148e2e673)
> ![image](https://github.com/user-attachments/assets/b715c79b-fd36-47d6-bd6a-2d5fb0ccd7a7)

> [!CAUTION]
>  Lo ideal es pedir al jefe de equipo o a otro miembro del equipo que revise el código para asegurarse de que los cambios son aceptables.

Compruebe que se han añadido archivos.
> ![image](https://github.com/user-attachments/assets/df1e9a32-a598-4c1f-93ec-ab5725076953)

Compruebe que se ha actualizado el historial de commit.
> ![image](https://github.com/user-attachments/assets/7f063b7c-1274-43b2-9c72-b8db493fa1ba)
> ![image](https://github.com/user-attachments/assets/0eab55e7-00ab-48db-a43b-3c4a5b3c946e)

### PASO8: Eliminar el branch de trabajo fusionado en GitHub.

> ![image](https://github.com/user-attachments/assets/52209efc-3b36-461d-b04d-f478bbac4383)

### PASO9: Eliminar el branch de trabajo fusionado en el repositorio local.
Para eliminar un branch, ejecute el comando `branch` con la opción `-d`.
> ```
> $ git branch -d <nombre de branch>
> ```

## Actualizar el repositorio local con `pull`
Utilice `pull` para reflejar los commits realizados por otros miembros en su repositorio local.

Como `push`, `<repositorio>` especifica el repositorio remoto y `<refspec>` el branch.
```
$ git pull <repositorio> <refspec>...
```

Ejecute el siguiente comando para reflejar el último estado del branch `main` del repositorio remoto en el repositorio local.
```
git checkout main
```
```
git pull origin main
```
> ![image](https://github.com/user-attachments/assets/a8df4b3b-3711-439f-b41a-37b348e47dab)

Compruebe que hay commits y archivos creados por otros miembros con los siguientes comandos.
```
git log
```
```
ls -l
```
> ![image](https://github.com/user-attachments/assets/d83c639a-543e-40c4-a995-62c2023bc688)

## Tarea2: Añadir mensajes de felicitación a los perfiles de otros miembros
Añada un mensaje de felicitación al **perfil de alguien cuyo cumpleaños sea uno después del suyo**.
- Para empezar, cree un branch del tema con el nombre `celebracion-"nombre de su compañero"` y muévase a ese branch
  ![image](https://github.com/user-attachments/assets/06e5d65c-c75a-4515-b815-c10f2bce0670)
- Añada un mensaje de felicitación al perfil de la persona cuyo cumpleaños es uno después del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
  ![image](https://github.com/user-attachments/assets/dd8f87b8-ba5d-44ad-a5c4-9cd0b2278bfc)
- Suba el cambio al repositorio remoto con `push`.
  ![image](https://github.com/user-attachments/assets/e9e9f46b-68c4-44a4-9204-cc2831db3935)
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.
- Fusione el `Pull Request` creado.
- Eliminar el branch de trabajo fusionado en GitHub.
- Eliminar el branch de trabajo fusionado en el repositorio local.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.

## Tarea3: Añadir una petición de regalo al perfil de otro miembro
Añada **lo que le gustaría recibir como regalo** al perfil de **alguien cuyo cumpleaños sea uno después del suyo**.
- Para empezar, cree un branch del tema con el nombre `peticion-regalo-"su compañro"` y muévase a ese branch
- Añada lo que le gustaría recibir como regalo al perfil de la persona cuyo cumpleaños es uno **antes** del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
- Suba el cambio al repositorio remoto con `push`.
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.

En el archivo que acabas de editar, haz una nueva línea y añade **lo que quieras como segundo regalo**.
- Añada **lo que quieras como segundo regalo** al perfil de la persona cuyo cumpleaños es uno **antes** del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
- Suba el cambio al repositorio remoto con `push`.
- Abra la `Pull Request` que acaba de crear y compruebe que se ha añadido el commit.
- Fusione el `Pull Request` creado.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.



<details>
<summary>Ejercicio extra</summary>

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

</details>
