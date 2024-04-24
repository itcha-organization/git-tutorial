# Tutorial de compartir repositorios

## Cree un repositorio remoto en GitHub

Primero, acceda a github e inicie sesión.
![https://github.com/](https://github.com/)

Haga clic en `el icono +` > `New repository`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac3cd9c5-8fd9-4f6b-8732-e292b90aa612)

Introduzca el "Repository" y la "Description", seleccione acceso `Private` y pulse el botón `Create repository`. <br>
Aquí, introduje `tutorial-repo` en el nombre y `para tutorial de repositorio remoto` en la descripción.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a794490a-00b3-4f51-8c85-ecaeb712a201)

Se añade un nuevo repositorio, como se muestra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/667d04d7-7d00-444d-8dad-7396f8637abe)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/afc592c6-b1c0-4bf0-87c4-9c530ca8e884)

## Realiza un push contra el repositorio remoto.

### Repaso: Cree un repositorio local y realize el primer commit.

Siga los siguientes comandos, cree un repositorio local llamado `tutorial-repo` y un archivo llamado `sample.txt` y realize el primer commit. <br>
Para el contenido de `sample.txt`, introduzca lo siguiente.

```
Tutorial de compartir repositorios
```

〇Lista de comandos
```
$ mkdir ~/tutorial-repo
$ cd ~/tutorial-repo
$ git init
$ nano sample.txt
$ cat sample.txt
$ git add sample.txt
$ git status
$ git commit -m "first commit"
$ git status
$ git log
```

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/bf0fb11c-a9db-439e-be40-76f98d5e6a96)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/4a96aec4-24e1-4976-a0bd-48e2914250a3)

### Registrar un repositorio remoto y realizar un push.

Ejecute push para enviar el historial del repositorio local al repositorio remoto.

Se puede nombrar y registrar la dirección del repositorio remoto.<br>
Grábala para no tener que introducir una larga dirección de repositorio remoto cada vez que realice un push.<br>
En primer lugar, registre un repositorio remoto con el nombre `origin` y, a continuación, realice un push.

Para añadir un repositorio remoto, utilice el comando `remoto`. `<nombre>` es el nombre del registro y `<url>` es la URL del repositorio remoto.

```
$ git remote add <nombre> <url>
```

Ejecute el siguiente comando para registrar la URL del repositorio remoto creado en la página anterior con el nombre `origin`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2f232723-6a7a-4366-8e50-fbba09422165)

```
$ git remote add origin ★¡Pegue su propia url!★
```

Ejemplo:
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/7288cc06-cdce-4c3e-b099-01ca867d56b2)

___
##### Consejo
Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado `origin`.<br>
Por este motivo, es habitual denominar a los repositorios remotos `origin`.
___

Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
<repositorio> especifica el repositorio remoto al que hacer push y <refspec> el branch a el que hacer push.

```
$ git push <repositorio> <refspec>...
```

Ejecute el siguiente comando para realizar un push contra el repositorio remoto `origin`.<br>
Si especifica `-u` como opción, puede omitir especificar el nombre de la rama la próxima vez.<br>
Sin embargo, al hacer push contra el primer repositorio remoto vacío, no puede omitir el nombre del repositorio remoto o el nombre del branch.

```
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 250 bytes | 62.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/tutorial-repo.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

Abra la página de Github.<br>
Compruebe que el repositorio se ha actualizado y que se ha añadido archivo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9fd6ec3a-3ebd-4aae-a77b-b7a0477f2f63)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/0b5a1b6a-816d-4009-b7c1-d2e0dea1e566)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/df7e7c02-a9a6-46be-ae55-98755e2b984c)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9d945b0b-3f4e-41f1-9b88-8b1b4a235543)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/de8ddabe-1b00-4f72-bf9a-0b3fd522d28a)

## Clonar repositorios remotos.

A continuación, clonee el repositorio remoto como si fueras otro usuario y crea un repositorio local `tutorial-repo-clone`.

Utilice el comando `clone` para clonar un repositorio. "repositorio" es la URL del repositorio remoto y "directorio" es el nombre del directorio a clonar.

```
$ git clone <repositorio> <directorio>
```

El siguiente comando replice el repositorio remoto en el directorio actual con el nombre de directorio `tutorial-repo-clone`.

```
$ git clone ★¡Pegue su propia url!★ ~/tutorial-repo-clone
```

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c19dc47e-8cd7-488f-9eb0-bb6f3414f040)

Compruebe que `sample.txt` con el siguiente contenido existe en el repositorio duplicado `tutorial-repo-clone`.

```
$ cat  ~/tutorial-repo-clone/sample.txt
Tutorial de compartir repositorios
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/32e7fea6-75dc-4b9a-9f29-a9c63b2645ff)

## Realice un push desde el repositorio clonado.

También puede realizar un push desde el repositorio local que ha clonado y creado.

Primero, añade el contenido al archivo `sample.txt` en el directorio del repositorio `tutorial-repo-clone` que has duplicado, y luego haga un commit.

```
Tutorial de compartir repositorios
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
```
```
$ cd ~/tutorial-repo-clone/
$ nano sample.txt
$ git add sample.txt
$ git commit -m "Añadida descripción de push, clone y pull"
[master 06da7ca] Añadida descripción de push, clone y pull
 1 file changed, 3 insertions(+)
```

A continuación, realice un push para reflejar estos cambios en el repositorio remoto.

```
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 428 bytes | 142.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/tutorial-repo.git
   bf8d348..06da7ca  master -> master
```


___
##### Consejo
En el repositorio clonado, se puede omitir el parámetro `origin master` de `push`.<br>
Porque cuando ejecutas el comando `clone`, establece valores predeterminados en el archivo de configuración `.git/config`.

```
$ cat .git/config
 ～omisión ～
[remote "origin"]
        url = git@github.com:kkk-commit/tutorial-repo.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
```
___


Abre la página del repositorio `tutorial-repo` en Github.<br>
Asegúrese de que el commit se añade al historial.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2b7499ff-d6fe-46ba-80cf-964ff9ad57e3)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/1f903017-3244-475f-8234-020b81b380fd)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ae189935-073c-4138-be95-c291e3bf07b5)

## Ejecute un pull para obtener los cambios en el repositorio remoto.

Obtener los últimos cambios del repositorio remoto en el repositorio local `tutorial-repo`.

Tomemos el contenido empujado desde `tutorial-repo-clone` al repositorio remoto e importémoslo a `tutorial-repo`.

Utilice el comando `pull` para realizar un pull. Si omite el nombre del repositorio, el pull se realiza contra el repositorio registrado con el nombre `origen`.

```
$ git pull <repositorio> <refspec>...
```

En primer lugar, ejecute el siguiente comando para ir al repositorio `tutorial-repo`.<br>
Compruebe el historial de commits y el contenido de los archivos en `tutorial-repo`.

```
$ cd ~/tutorial-repo
$ git log
commit bf8d3486e91e4dbc0bae0619fbef92de47e2ec21 (HEAD -> master, origin/master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Mon Apr 15 11:29:51 2024 -0600

    first commit
$ cat sample.txt
Tutorial de compartir repositorios
```

A continuación, realice un pull.

```
$ git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 408 bytes | 17.00 KiB/s, done.
From github.com:kkk-commit/tutorial-repo
 * branch            master     -> FETCH_HEAD
   bf8d348..06da7ca  master     -> origin/master
Updating bf8d348..06da7ca
Fast-forward
 sample.txt | 3 +++
 1 file changed, 3 insertions(+)
```

Compruebe el historial de commits y el contenido de los archivos otra vez.<br>
Se ha añadido el commit en el historial. Además, se ha añadido el contenido del archivo.

```
$ git log
commit 06da7ca7a974dc991b87cd3db1108ebf7b1cfb2f (HEAD -> master, origin/master)
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Tue Apr 16 08:55:45 2024 -0600

    Añadida descripción de push, clone y pull

commit bf8d3486e91e4dbc0bae0619fbef92de47e2ec21
Author: Kyo Onuma <kyo.onuma@itcha.edu.sv>
Date:   Mon Apr 15 11:29:51 2024 -0600

    first commit

$ cat sample.txt
Tutorial de compartir repositorios
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/33733745-7be0-4b6b-8dc9-396c2c33ec0d)
