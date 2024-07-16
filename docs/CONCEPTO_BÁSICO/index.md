# git-tutorial-básico

## Concepto básico de Git

### Control de versiones mediante Git

Git le permite guardar el estado de un archivo como un historial de actualizaciones siempre que quiera.<br>
Esto le permite revertir un archivo una vez editado a un estado anterior y ver las diferencias en las partes editadas del archivo.

Además, si intenta sobrescribir el último archivo editado por otra persona con un archivo editado a partir de un archivo anterior, recibirá una advertencia cuando suba el archivo al servidor.<br>
Por lo tanto, no se producirán errores como sobrescribir sin saberlo las ediciones de otra persona.

* Muchos de nosotros hemos utilizado en algún momento de nuestras vidas la versión de control de versiones de añadir una fecha a un nombre de archivo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/87797550-9ff7-4639-8ba9-347d6330c152)

### Repositorios para la gestión del historial

Un repositorio es el elemento más básico de Git. Es más fácil imaginarlos como una carpeta del proyecto.<br>
Un repositorio contiene todos los archivos del proyecto (incluida la documentación) y almacena el historial de revisión de cada archivo.

Los repositorios Git pueden dividirse en dos tipos: repositorios remotos y repositorios locales.

* Repositorios remotos<br>
  Se trata de repositorios ubicados en un servidor dedicado y compartido por varios usuarios.
* Repositorios locales<br>
  Son repositorios que se colocan en su propia máquina para el uso de usuarios individuales.

Al dividir el repositorio en dos tipos, remoto y local, puede utilizar el repositorio local para sus cambios del código en la máquina que tenga a mano.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c4dce745-8dae-4450-97a1-08ff77d102f9)

### commit de los cambios (Commit)

Para registrar adiciones y cambios a ficheros y directorios en el repositorio, se realiza una operación llamada commit.

Cuando realiza una commit, se crea una commit (o revisión) en el repositorio, que registra la diferencia entre la última commit y el estado actual.

Estos commits se almacenan en el repositorio en orden cronológico, como se muestra en el siguiente diagrama.<br>
Rastreando estos commits desde el último, puede ver la historia de los cambios pasados y su contenido.

* HEAD<br>
  Puntero que indica dónde está trabajando actualmente, normalmente la commit más reciente en el extremo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a335c831-daef-4829-8455-471cc7f304a2)

### Árbol de trabajo y staging (o índice)

En Git, el directorio en el que está trabajando, que está bajo el control de Git, se llama árbol de trabajo.

Con el comando `git add` enviamos los cambios a staging (o índice), que es un estado intermedio en el que se van almacenando los archivos a enviar en el commit.<br>
Finalmente con `git commit` lo enviamos al repositorio local.

Si queremos colaborar con otros, con `git push` subimos los archivos a un repo remoto y mediante `git pull` podríamos traer los cambios realizados por otros en remoto hacia nuestro directorio de trabajo.

Si comenzamos trabajando en remoto, lo primero que hacemos es un clon de la información en el directorio local.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/48f8b23b-2eb9-4652-bf49-0847efe6fb0c)

## Configuración

Si ya ha completado la configuración, puede practicar los comandos en siguiente pagina.<br>
https://learngitbranching.js.org/?locale=es_AR
___

### Instalación y configuración inicial de Git en Windows

Siga los pasos del siguiente artículo para instalarlo.<br>
https://www.neoguias.com/instalar-git-windows/

Una vez instalado, inicia Menú Inicio > Todos los programas > Git > Git Bash.

La configuración de git se registra en un archivo .gitconfig que se crea en el directorio home del usuario. Puede editar el archivo directamente, pero aquí usaremos el comando config para configurar los ajustes. <br>
Establecer el nombre de usuario y la dirección de correo electrónico, que se registran en commit.
```
$ git config --global user.name "<Nombre de usuario>"
$ git config --global user.email "<Dirección de correo electrónico de ITCHA>"
```
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/139957ee-cf22-44c2-885c-1cc08785f529)

### Creación de una cuenta en GitHub

Siga los pasos del siguiente artículo para creala.<br>
※Más adelante, podrá vincular su dirección de correo electrónico ITCHA a su cuenta. Por lo tanto, puede utilizar la dirección de cualquier correo electrónico.<br>
https://docs.github.com/es/get-started/start-your-journey/creating-an-account-on-github#signing-up-for-a-new-personal-account

### Cómo generar una clave SSH y agregarla a GitHub

##### Cómo generar una nueva clave SSH

Ejecute el siguiente comando, reemplazando el parámetro de segundo opcion por tu dirección de correo.<br>
Tras ejecutar el comando, aparecen varias preguntas. No escriba nada y pulse Intro.
```
$ ssh-keygen -t ed25519 -C "Dirección de correo electrónico de ITCHA"
```

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e343c7e6-1b6d-4410-b1f5-906d8617fb50)


#### Cómo agregar una clave SSH a tu cuenta de GitHub

Primero, accede a tu cuenta de GitHub mediante tu navegador y accede a la configuración de tu cuenta haciendo clic en la foto de perfil de la parte superior derecha del menú y luego en Configuración (Settings).
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6c618047-5948-49c7-bfb2-482feba52c99)

Haz clic en la opción `SSH and GPC keys` que verás en la sección `Access` del menú de la izquierda.<br>
Haz clic en `New SSH Key`.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/b381e960-bd38-4bbf-822c-4bb75093f2a1)

Ahora vuelve a GitBash.Ejecute el siguiente comando para copiar la clave que es el contenido del achivo `id_ed25519.pub`.<br>
Este comando copiará el contenido de `id_ed25519.pub`, que podrá pegarse con control + v.
```
$ clip < ~/.ssh/id_ed25519.pub
```

Introduce un nombre para la clave en el campo `Title`. Luego pega la clave SSH que has copiado anteriormente en el campo Key, dejando seleccionada la opción Key type.
Finalmente haz clic en el botón `Add SSH key`. Si se te solicita la contraseña de tu cuenta, introdúcela.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/499d1602-c212-4718-999d-a4a5da1bc521)

Ejecute el siguiente comando para comprobar la conexión
```
$ ssh -T git@github.com
```
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/25d3b534-44d2-497b-8689-77f1397882b4)

###### Página de referencia.
[Documentación de GitHub:Conectar a GitHub con SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh)<br>
[Cómo generar una clave SSH y agregarla a GitHub](https://www.neoguias.com/generar-clave-ssh-agregar-github/)


