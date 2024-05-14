# Guía de operaciones

## Duplicar repositorios remotos.`Operación única por primera vez`

Hay dos formas de crear un repositorio local en Git, una usando el comando `git init` y la otra usando este comando `git clone`.<br>
Para el desarrollo en equipo, en la mayoría de los casos se utiliza `git clone` para clonar el repositorio remoto y crear un repositorio local.

Ejecute el siguiente comando para crear un repositorio local que replique el repositorio remoto.
Además, en el caso de `git clone`, el repositorio remoto `origin` se registra automáticamente, así que compruébalo también.

```
$ git clone <repositorio> <directorio>
$ cd <directorio>
$ git remote -v
```

Se trata de un procedimiento que sólo es necesario realizar la primera vez que se crea un nuevo repositorio.

## Crear Issues

### Resumen de `Issues`

`Issues` es una función para describir y gestionar informes de errores, peticiones de funciones y tareas.<br>
Algunos ejemplos de ventajas concretas son

* **Seguimiento y gestión de problemas:** <br>
  GitHub Issues permite seguir y gestionar eficazmente problemas y tareas dentro de un proyecto. Puedes describir claramente los problemas y organizarlos con etiquetas y hitos.
* **Colaboración:** <br>
  Cuando trabajan varias personas en un proyecto, GitHub Issues facilita la colaboración. Se pueden hacer comentarios en los problemas, asignarlos a personas y relacionarlos con solicitudes de extracción de manera sencilla.
* **Búsqueda y filtrado:** <br>
  Los Issues cuentan con funciones de filtrado y búsqueda, lo que facilita el acceso rápido a la información necesaria y hace que el seguimiento de problemas sea más fácil incluso en proyectos grandes.

### Cómo utilizar Issues

Seleccione `Issues` en la pestaña correspondiente del proyecto en GitHub.Haga clic en `New issue`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2e53b562-cd03-476d-a439-ca8a7fa272a2)

Rellene el título y el contenido del `issue` y haga clic en `Submit new issue`.<br>
El siguiente texto es una plantilla de contenido. Cópielo, péguelo y utilícelo.

```
### Descripción de la tarea

* Para gestionar Carrera con estado, es necesario añadir estado al modelo de Carrera.
* Para gestionar Ciclo con codigo, es necesario añadir codigo al modelo de Ciclo.
```

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/392fa867-efb2-4ff4-b6ab-a3a7f61254b6)

## Editar código en el repositorio local.

Crea un nuevo branch de trabajo para el `issue` registrado y empieza a editar el código.<br>
Los branches se nombran según el formato: 

```
feature/issue-<Número de issue>-<Título abreviado de la issue>
```

Tras crear una pull request, el flujo de trabajo se configura para detectar el nombre del branch y vincular automáticamente la incidencia numerada correspondiente.

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c3831cc1-48e5-4d34-add0-a6fd386cdb12)

Cuando la modificación esté completa, crea un commit. Añade `#` y `Número de issue` antes del mensaje del commit.<br>
El comando tiene la siguiente forma: 

```
git commit -m "#<Número de issue> <Mensaje del commit>"
```

De este modo, el issue puede asociarse al commit en GitHub.

Una vez finalizado el trabajo, utilice el siguiente comando para realizar un push.

```
git push origin -u <el nombre del branch de trabajo>
```

## Crear un pull request

Cree un pull request en GitHub.Si es necesaria una revisión, pida a un colega que la revise.<br>
Si no hay problemas, fusione el pull request.

Cuando se fusiona el pull request, se cierra el `issue` asociado.

## Actualice el branch master en el repositorio local.

El `branch master` debe estar siempre actualizada, ya que branches de trabajo se crean a partir del `branch master`.<br>
Utilice el siguiente comando para ir a `branch master` y actualizarlo con el repositorio remoto.

Después de Actualizar `branch master` en el repositorio local, cree un branch de trabajo para las siguientes tareas.

```
git checkout master
git pull origin master
```

