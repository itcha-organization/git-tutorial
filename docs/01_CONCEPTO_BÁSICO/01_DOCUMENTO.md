# Concepto básico de Git

## Control de versiones mediante Git

Git le permite guardar el estado de un archivo como un historial de actualizaciones siempre que quiera.<br>
Esto le permite revertir un archivo una vez editado a un estado anterior y ver las diferencias en las partes editadas del archivo.

Además, si intenta sobrescribir el último archivo editado por otra persona con un archivo editado a partir de un archivo anterior, recibirá una advertencia cuando suba el archivo al servidor.<br>
Por lo tanto, no se producirán errores como sobrescribir sin saberlo las ediciones de otra persona.

> Muchos de nosotros hemos utilizado en algún momento de nuestras vidas la manera de control de versiones de añadir una fecha a un nombre de archivo. Con Git, no tendrá que ocuparse de estos molestos trámites.
  ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/87797550-9ff7-4639-8ba9-347d6330c152)

## Repositorios para la gestión del historial

Un repositorio es el elemento más básico de Git. Es más fácil imaginarlos como una carpeta del proyecto.<br>
Un repositorio contiene todos los archivos del proyecto (incluida la documentación) y almacena el historial de revisión de cada archivo.

Los repositorios Git pueden dividirse en dos tipos: repositorios remotos y repositorios locales.

* Repositorios remotos<br>
  Se trata de repositorios ubicados en un servidor dedicado y compartido por varios usuarios.
* Repositorios locales<br>
  Son repositorios que se colocan en su propia máquina para el uso de usuarios individuales.

Al dividir el repositorio en dos tipos, remoto y local, puede utilizar el repositorio local para sus cambios del código en la máquina que tenga a mano.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c4dce745-8dae-4450-97a1-08ff77d102f9)

## ***Commit*** de los cambios

En Git, un ***commit*** es una instantánea de los cambios en un proyecto. Se usa para guardar adiciones y cambios a archivos y directorios en el repositorio.

Cuando se crea un commit en el repositorio, se registra la diferencia entre el commit anterior y el estado actual.

Estos commits se almacenan en el repositorio en orden cronológico, como se muestra en el siguiente diagrama.<br>
Rastreando estos commits desde el último, puede ver la historia de los cambios pasados y su contenido.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a335c831-daef-4829-8455-471cc7f304a2)

> [!NOTE]
>  ***HEAD:***
> Es un puntero que indica dónde está trabajando actualmente, normalmente el commit más reciente en el extremo.

## ***Working tree*** y ***staging*** (o **índice**)

En Git, el directorio en el que está trabajando, que está bajo el control de Git, se llama ***working tree***.

Con el comando `git add` enviamos los cambios a ***staging*** (o **índice**), que es un estado intermedio en el que se van almacenando los archivos a enviar en el commit.<br>
Finalmente con `git commit` lo enviamos al repositorio local.

Si queremos colaborar con otros, con `git push` subimos los archivos a un repo remoto y mediante `git pull` podríamos traer los cambios realizados por otros en remoto hacia nuestro directorio de trabajo.

Si comenzamos trabajando en remoto, lo primero que hacemos es un clon de la información en el directorio local.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/48f8b23b-2eb9-4652-bf49-0847efe6fb0c)
