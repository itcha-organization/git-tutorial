# TUTORIAL

## Comandos Git básicos
Actualmente, existen muchas herramientas GUI que facilitan el desarrollo con Git.  
Sin embargo, en esta capacitación utilizaremos GitBash y comandos por las siguientes tres ventajas:  

- Al usar comandos en lugar de herramientas GUI, se puede comprender mejor el funcionamiento interno de Git y el mecanismo de control de versiones.  
- Es posible utilizar los mismos comandos de Git en cualquier sistema operativo (Windows, Linux, Mac).  
- Se pueden emplear opciones avanzadas que no están disponibles en las herramientas GUI.

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
> [!NOTE]
>  El comando `init` crea el directorio `.git`. El directorio `.git` contiene los archivos necesarios para que Git funcione.
> > ![image](https://github.com/user-attachments/assets/c746a558-fc7c-403e-b57c-9ebdf94b475f)
___

### Guardar los Cambios en el Repositorio: status, add, commit, log, diff
Ejecute el siguiente código para abrir VS Code en el directorio actual.
```
code .
```
> ![image](https://github.com/user-attachments/assets/48e17333-b6d1-45e5-8874-b1a9e9b5c8e9)

Cree un archivo de texto llamado `sample.txt` en el directorio `tutorial`. 
<br>Abra el archivo y pegue el siguiente texto y guárdelo.
```
Comandos Git básicos
<contenido>
```
> ![image](https://github.com/user-attachments/assets/86c12396-61af-4c57-8392-d2701b6fbb9f)

Utiliza el comando `status` para comprobar el árbol de trabajo y el estado de los staging (índice)s de los directorios bajo control Git.<br>
Ejecuta el comando `status` para comprobar el estado del directorio `tutorial`.
```
git status
```
> ![image](https://github.com/user-attachments/assets/d482e4e0-4244-4d4c-ac77-a21fd28da8f7)

Utilice el comando `add` para registrar archivos en el staging (índice). <br>
El `<archivo>` especifica el archivo que se registrará en el staging (índice). Se pueden especificar varios archivos, separados por espacios.
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
iniciar un área de trabajo (ver también: tutorial de ayuda de git)
   init Crear un repositorio Git vacío o reinicializar uno existente

trabajar en el cambio actual (ver también: git help everyday)
   add Añadir el contenido de un archivo al índice

examinar el historial y el estado (ver también: git help revisions)
   log Mostrar los logs de commit
   status Mostrar el estado del árbol de trabajo

aumentar, marcar y modificar el historial común
   commit Registrar los cambios en el repositorio
```
> ![image](https://github.com/user-attachments/assets/24d9b9c9-a2a4-41b9-bca3-1f9f7c4d325f)

El comando `diff` también puede utilizarse para revisar los cambios.<br>
Las filas añadidas se indican con texto verde y las suprimidas con texto rojo.
```
git diff
```
> ![image](https://github.com/user-attachments/assets/2120db71-c122-412e-a032-fa7229cf8e8d)

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

### Ver contenido de commits anteriores: show

Cada commit tiene un `hash` que la identifica de forma única.
![image](https://github.com/user-attachments/assets/eb177490-7c71-4af5-af94-3152b0f1e28b)

El comando `show` permite ver lo que ha cambiado en un commit. La sintaxis es la siguiente, con el hash como parámetro.
```
$ git show <hash>
```
> Ejemplo:
> <br>
> ![image](https://github.com/user-attachments/assets/68722d6c-b575-40fa-a0a0-d2d0cc97a0b6)

Con Git, también se pueden realizar operaciones avanzadas como revertir un archivo a un estado de commit específico o restablecer un commit.
<br>Si le interesa, puedes investigar y experimentar con la siguiente documentación oficial.

Documentación oficial: https://git-scm.com/docs
