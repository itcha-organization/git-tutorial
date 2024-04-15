# Tutorial de compartir repositorios

## Cree un repositorio remoto en GitHub

Primero, acceda a github e inicie sesión.
https://github.com/

Haga clic en `el icono +` > `New repository`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac3cd9c5-8fd9-4f6b-8732-e292b90aa612)

「Repository」と「Description」
Introduzca el "Repository" y la "Description", seleccione acceso `Private` y pulse el botón `Create repository`. <br>
Aquí, introduje `tutorial-repo` en el nombre y `para tutorial de repositorio remoto` en la descripción.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a794490a-00b3-4f51-8c85-ecaeb712a201)

Se añade un nuevo repositorio, como se muestra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/667d04d7-7d00-444d-8dad-7396f8637abe)

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

Ejecute el siguiente comando para realizar un push contra el repositorio remoto `origen`.<br>
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

## Clonar repositorios remotos.

A continuación, clonee el repositorio remoto como si fueras otro usuario y crea un repositorio local `tutorial-repo-clone`.

Utilice el comando `clone` para clonar un repositorio. <repositorio> es la URL del repositorio remoto y <directorio> es el nombre del directorio a clonar.

```
$ git clone <repositorio> <directorio>
```

El siguiente comando replice el repositorio remoto en el directorio actual con el nombre de directorio `tutorial-repo-clone`.

```
$ git clone ★¡Pegue su propia url!★ tutorial-repo-clone
Cloning into 'tutorial2'...
Username: <メールアドレス>
Password: <パスワード>
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Unpacking objects: 100% (3/3), done.
```

Compruebe que `sample.txt` con el siguiente contenido existe en el repositorio duplicado `tutorial-repo-clone`.

```
Tutorial de compartir repositorios
```
