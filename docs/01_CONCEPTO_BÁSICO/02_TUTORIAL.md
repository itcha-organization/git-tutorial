# TUTORIAL

## Comandos Git básicos
Actualmente, existen muchas herramientas GUI que facilitan el desarrollo con Git.  
Sin embargo, en esta capacitación utilizaremos GitBash y comandos por las siguientes tres ventajas:  

- Al usar comandos en lugar de herramientas GUI, se puede comprender mejor el funcionamiento interno de Git y el mecanismo de control de versiones.  
- Es posible utilizar los mismos comandos de Git en cualquier sistema operativo (Windows, Linux, Mac).  
- Se pueden emplear opciones avanzadas que no están disponibles en las herramientas GUI, como `git log --graph --oneline --all`.

### Crear un nuevo repositorio: init

Crea un nuevo repositorio localmente. <br>
Ejecute el siguiente comando para crear un directorio vacío llamado `tutorial` y colóquelo bajo control Git.<br>
Seguiremos utilizando este directorio en tutoriales posteriores.
```
mkdir ~/tutorial
```

Para poner el directorio `tutorial` bajo el control de Git, vaya a ese directorio y utilice el comando `init`.
```
cd ~/tutorial
```
```
git init
```
> ![image](https://github.com/user-attachments/assets/47131400-00b9-437b-bca5-8c0e4c59b9c7)
___
##### Consejo
El comando `init` crea el directorio `.git`. El directorio `.git` contiene los archivos necesarios para que Git funcione.<br>
> ![image](https://github.com/user-attachments/assets/c746a558-fc7c-403e-b57c-9ebdf94b475f)
___

### Guardar los Cambios en el Repositorio: status, add, commit, log, diff

Cree un fichero de texto llamado `sample.txt` en el directorio `tutorial`. 
```
nano sample.txt
```

Se abrirá un editor, pegue el siguiente texto y guárdelo.
Para guardar, teclee las siguientes teclas en tres pasos: `Ctrl + X`, `Y`, `Intro`
```
Comandos Git básicos
```
> ![image](https://github.com/user-attachments/assets/9847cf90-a418-4ae7-9101-dada31863fc0)

Utiliza el comando `status` para comprobar el árbol de trabajo y el estado de los staging (índice)s de los directorios bajo control Git.<br>
Ejecuta el comando `status` para comprobar el estado del directorio `tutorial`.
```
git status
```
> ![image](https://github.com/user-attachments/assets/d482e4e0-4244-4d4c-ac77-a21fd28da8f7)

Utilice el comando `add` para registrar ficheros en el staging (índice). <br>
El `<archivo>` especifica el archivo que se registrará en el staging (índice). Se pueden especificar varios ficheros, separados por espacios.
```
$ git add <archivo>..
```

En realidad, ejecute el siguiente comando para añadir `sample.txt` al staging (índice) y compruébelo.<br>
El archivo `sample.txt` ha sido añadido al staging (índice) y está listo para ser commit.
```
git add sample.txt
```
```
git status
```
> ![image](https://github.com/user-attachments/assets/a78c2215-2784-4d0f-9a64-aa547b159e66)

El siguiente paso es crear un commit y guardar la modificación ejecutando el comando `commit`.
<br>El formato del comando `commit` es.
```
$ git commit -m "<Comentario>"
```

Ejecute el comando `commit` para hacer commit con un comentario `initial commit`.
```
git commit -m "initial commit"
```

A continuación, ejecute el comando `status` y compruebe que no aparece ninguna modificación.
```
git status
```
> ![image](https://github.com/user-attachments/assets/ae93fdd4-bc8f-4e07-8625-9afeaa84d796)


Compruebe el historial de cambios del repositorio. Utilice el comando `log` para ver el historial de cambios del repositorio.
```
git log
```
> ![image](https://github.com/user-attachments/assets/2fe23450-4a56-490b-bc46-889ddf8e1b69)

A continuación, editamos `sample.txt` y hacemos commit de nuevo.

Añade `sample.txt` al siguiente texto.
```
start a working area (see also: git help tutorial)
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index

examine the history and state (see also: git help revisions)
   log       Show commit logs
   status    Show the working tree status

grow, mark and tweak your common history
   commit    Record changes to the repository
```
> ![image](https://github.com/user-attachments/assets/40591c83-49bf-460d-a8b6-90b2997659f6)

El comando `diff` también puede utilizarse para revisar los cambios.<br>
Las filas añadidas se indican con texto verde y las suprimidas con texto rojo.
```
git diff
```
> ![image](https://github.com/user-attachments/assets/65000ccc-7c91-4f4e-9c22-d0a4050bc02c)

Ejecute el siguiente comando para añadir `sample.txt` al staging (índice) y compruébelo.<br>
```
git status
```
```
git add sample.txt
```
```
git status
```
> ![image](https://github.com/user-attachments/assets/b8a184f5-c258-49c4-9383-cf0c140ddebe)


El archivo `sample.txt` ha sido añadido al staging (índice) y está listo para ser commit.

Ejecute el comando `commit` para hacer commit con un comentario `Descripción adicional del comando`.
<br>A continuación, ejecute el comando `status` y compruebe que no aparece ninguna modificación.
<br>Por fin, compruebe el historial de cambios del repositorio utilizando el comando `log`
```
git commit -m "Descripción adicional del comando"
```
```
git status
```
```
git log
```
> ![image](https://github.com/user-attachments/assets/a94925d5-4318-41af-935b-65a3737e207f)
