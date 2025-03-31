# Tutorial 1: Comparta su perfil en un repositorio remoto

## Clonar un repositorio remoto de GitHub y crear un repositorio local

Abra el siguiente repositorio remoto de GitHub en otra pestaña.
<br>
https://github.com/kkk-commit/proyecto-presentacion-perfil

Utilice el comando `clone` para clonar un repositorio. `<repositorio>` es la URL del repositorio remoto y `<directorio>` es el nombre del directorio a clonar.

> ```
> $ git clone <repositorio> <directorio>
> ```

En GitBash, el siguiente comando clona el repositorio remoto `proyecto-presentacion-perfil` y crea un repositorio local.
```
git clone git@github.com:kkk-commit/proyecto-presentacion-perfil.git ~/proyecto-presentacion-perfil
```
> ![image](https://github.com/user-attachments/assets/6aaa708a-0c95-4900-9efc-db8f4a270566)

Ejecute los siguientes comando para ir al repositorio local clonado y compruebe el historial de _commit_ y el archivo `README.md`.
```
cd ~/proyecto-presentacion-perfil
```
```
git log
```
```
cat README.md
```
> ![image](https://github.com/user-attachments/assets/bb81042a-894d-45a7-8214-147f1d70290e)

## Crear un archivo de perfil en el repositorio local y ejecutar commit.

Para empezar a trabajar, cree un branch del tema con el nombre `feature/perfil-"su nombre"` y muévase a ese branch.

> ![image](https://github.com/user-attachments/assets/1649cd37-ab9b-4c4a-a30e-c8597144e7b8)

> [!NOTE]
>  Normalmente, el nombre de un branch es
> <br>el prefijo `feature/` + un resumen de tareas separada por guiones,
> <br>por ejemplo `feature/funcion-login`,`feature/ui-modo-oscuro`.

> [!CAUTION]
>  Se desaconseja el uso de la `ñ` o de `caracteres acentuados(á, é, í, ó, ú)` en los nombres de branch.

Cree un archivo llamado `Perfil_"su nombre".md`, escribe su cumpleaños y guarde el archivo.

> ![image](https://github.com/user-attachments/assets/927179e2-48e6-4db2-ba16-a072da9cce58)
> ![image](https://github.com/user-attachments/assets/814c58db-29be-4745-9737-198d28193f17)

> [!NOTE]
>  `.md` es un archivo en formato Markdown, un tipo de lenguaje que puede convertir texto plano escrito en notación simple en HTML y otros formatos.

Cree un commit y guarda los cambios en el repositorio local.

> ![image](https://github.com/user-attachments/assets/3da79e72-217b-45dd-976a-dc6cd5b05dd9)

## Subir el cambio al repositorio remoto con `push`.

Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
`<repositorio>` especifica el repositorio remoto al que hacer push y `<refspec>` el branch a el que hacer push.

```
$ git push <repositorio> <refspec>...
```

Sustituya el segundo argumento del siguiente comando por el nombre de su propio branch y ejecute el comando.
```
git push origin "el nombre de su branch"
```
> ![image](https://github.com/user-attachments/assets/52f0f5bf-9f62-462b-89a5-52d9962a77b7)

> [!NOTE]
> **origin**:
> Si ejecutas `git clone`, el repositorio remoto tendrá `origin` como nombre por defecto.

## Comprobar branch subido en GitHub.
Abra el repositorio remoto de GitHub en su navegador y compruebe que se ha añadido el branch que ha subido.
<br>Repositorio remoto de GitHub: https://github.com/kkk-commit/proyecto-presentacion-perfil

> ![image](https://github.com/user-attachments/assets/0a299244-c40b-42d7-8459-d875defc0667)

## Crear ***Pull Request***
Vamos a crear un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.

Haga clic en `Compare & pull request`
> ![image](https://github.com/user-attachments/assets/0ad9089b-e7ef-4986-ac50-dfeedc71019f)

Asegúrese de que _base_(el branch de destino) es el branch `main` y _compare_(el branch de origen) es el branch que subió.
<br>
Después, Haga clic en `Create pull request`
> ![image](https://github.com/user-attachments/assets/40980a6f-d43f-4dd9-878a-f63626b5aa1e)

La siguiente imagen muestra el `Pull Request` creada.
> ![image](https://github.com/user-attachments/assets/7b8624d8-7c86-4d27-a3b1-3dbffd856648)

## Fusionar ***Pull Request***
Como esto es un tutorial, nos saltaremos la revisión del código y fusionaremos la `Pull Request`.

Haga clic en `Merge pull request`.
Después, Haga clic en `Confirm merge`.
> ![image](https://github.com/user-attachments/assets/ddcc7013-f1c5-4de2-b1e3-971148e2e673)
> ![image](https://github.com/user-attachments/assets/b715c79b-fd36-47d6-bd6a-2d5fb0ccd7a7)

> [!CAUTION]
>  Lo ideal es pedir al jefe de equipo o a otro miembro del equipo que revise el código para asegurarse de que los cambios son aceptables.

## Comprobar que los cambios se han incorporado al `main`
Compruebe que se han añadido archivos.
> ![image](https://github.com/user-attachments/assets/df1e9a32-a598-4c1f-93ec-ab5725076953)

Compruebe que se ha actualizado el historial de commit.
> ![image](https://github.com/user-attachments/assets/7f063b7c-1274-43b2-9c72-b8db493fa1ba)
> ![image](https://github.com/user-attachments/assets/0eab55e7-00ab-48db-a43b-3c4a5b3c946e)


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

Ejecute el siguiente comando para comprobar que se han añadido el historial de commit y los archivos.
```
git log
```
```
ls -l
```
> ![image](https://github.com/user-attachments/assets/d83c639a-543e-40c4-a995-62c2023bc688)

## Editar archivos creados por otros miembros
Añada un mensaje de felicitación al **perfil de alguien cuyo cumpleaños sea uno después del suyo**.
- Para empezar, cree un branch del tema con el nombre `feature/celebracion-"nombre de su compañero"` y muévase a ese branch
  ![image](https://github.com/user-attachments/assets/06e5d65c-c75a-4515-b815-c10f2bce0670)
- Añada un mensaje de felicitación al perfil de la persona cuyo cumpleaños es uno después del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
  ![image](https://github.com/user-attachments/assets/dd8f87b8-ba5d-44ad-a5c4-9cd0b2278bfc)
- Suba el cambio al repositorio remoto con `push`.
  ![image](https://github.com/user-attachments/assets/e9e9f46b-68c4-44a4-9204-cc2831db3935)
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.
- Fusione el `Pull Request` creado.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.

## Repaso: Editar archivos creados por otros miembros
Añada **lo que le gustaría recibir como regalo** al perfil de **alguien cuyo cumpleaños es uno antes que el suyo**.
- Para empezar, cree un branch del tema con el nombre `feature/peticion-regalo-"su compañro"` y muévase a ese branch
- Añada lo que le gustaría recibir como regalo al perfil de la persona cuyo cumpleaños es uno **antes** del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
- Suba el cambio al repositorio remoto con `push`.
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.
- Fusione el `Pull Request` creado.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.

# Tutorial 2: Crear un repositorio remoto.

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

Siga los siguientes comandos, cree un repositorio local llamado `tutorial-repo` y un archivo llamado `README.md` y realize el primer commit. <br>
Para el contenido de `README.md`, introduzca lo siguiente.
```
# tutorial-repo
```

〇Lista de comandos
```
$ mkdir ~/tutorial-repo
$ cd ~/tutorial-repo
$ git init
$ echo "# tutorial-repo" >> README.md
$ git status
$ git add sample.txt
$ git status
$ git commit -m "commit inicial"
$ git status
$ git log
```
> ![image](https://github.com/user-attachments/assets/d1c217a8-d573-4d4a-b7a8-24342571ad03)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/4a96aec4-24e1-4976-a0bd-48e2914250a3)

☆

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

El siguiente comando se puede utilizar para comprobar los repositorios remotos registrados.
```
$ git remote -v
```

Ejemplo:<br>
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2f524c6b-b72d-4e21-b353-f429e02be9d0)

___
##### Consejo
Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado `origin`.<br>
Por este motivo, es habitual denominar a los repositorios remotos `origin`.
___

Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
`<repositorio>` especifica el repositorio remoto al que hacer push y `<refspec>` el branch a el que hacer push.

```
$ git push <repositorio> <refspec>...
```

Ejecute el siguiente comando para realizar un push contra el repositorio remoto `origin`.<br>
Si utilizar `-u` como opción, puede omitir especificar el nombre del branch la próxima vez.<br>
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
