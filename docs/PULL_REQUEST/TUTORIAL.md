# Utiliza pull requests.

Ahora vamos a experimentar las pull requests en la práctica.
Como tema para pull requests, me gustaría añadir un proceso para ordenar el contenido de una lista al código con sólo un array listo en JavaScript.

## Preparar repositorios de muestras

Crear un repositorio en GitHub para experimentar pull requests.

Primero, acceda a github e inicie sesión.
![https://github.com/](https://github.com/)

Haga clic en `el icono +` > `New repository`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac3cd9c5-8fd9-4f6b-8732-e292b90aa612)

Introduzca el "Repository", seleccione acceso `Private` y pulse el botón `Create repository`. <br>
Aquí, introduje `pull-request-test` en el nombre.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/659fe9ac-89f4-49c4-9202-7da3ba1c7733)

Siga los siguientes comandos en Git Bash, cree un repositorio local llamado `pull-request-test` y un archivo llamado `sort.js` y realize el primer commit. <br>
Para el contenido de `sort.js`, introduzca lo siguiente.

```
var number = [19, 3, 81, 1, 24, 21];
console.log(number);
```

〇Lista de comandos
```
$ mkdir ~/pull-request-test
$ cd ~/pull-request-test
$ git init
$ nano sort.js
$ cat sort.js
$ git add sort.js
$ git status
$ git commit -m "first commit"
$ git status
$ git log
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/4662d59c-da56-4542-9e96-0b26a9309c06)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/f4d2e7e5-a41d-41b2-a08c-1fa3837332c1)

Ejecute el siguiente comando para registrar la URL del repositorio remoto creado en la página anterior con el nombre `origin`.<br>
El segundo comando es para comprobar que se ha registrado.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e8d14eb8-4153-47c7-bff4-878cff377898)

```
$ git remote add origin ★¡Pegue su propia url!★
$ git remote -v
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/0e8d0c81-3d20-413f-851b-b8d70bd2b6d8)

Ejecute el siguiente comando para realizar un push contra el repositorio remoto `origin`.<br>
Si especifica `-u` como opción, puede omitir especificar el nombre de la rama la próxima vez.<br>
Sin embargo, al hacer push contra el primer repositorio remoto vacío, no puede omitir el nombre del repositorio remoto o el nombre del branch.

```
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 265 bytes | 265.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:kkk-commit/pull-request-test.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

Abra la página de Github.<br>
Compruebe que el repositorio se ha actualizado y que se ha añadido archivo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e635cb29-8aef-46db-ac9a-dc6e85321a14)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/481f5451-08f4-4924-8057-53e84ac85b86)

## Modificación del código en un branch de tema.

### 1.Crear una branch de tema.

Primero, crea un branch en la que trabajar. Crea un branch llamada `add-sort-func`, ya que este es el proceso de ordenar un array.

```
$ git checkout -b add-sort-func
```

### 2.Modificar archivos y crear commits.

Modifique el archivo `sort.js` de la siguiente manera.

```
var sortNumber = function (number) {
   number.sort(function (a, b) {
       if (a == b) {
           return 0;
       }
       return a < b ? -1 : 1;
   });
};

var number = [19, 3, 81, 1, 24, 21];
sortNumber(number);
console.log(number);
```

Se completa la modificación y se crea un commit.

```
$ git add sort.js
$ git commit -m "Añadido proceso para ordenar matrices."
```

### 3.Realizar un push en branch de tema

Una vez completada la confirmación, realice un push al repositorio remoto.

```
$ git push -u origin add-sort-func
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/19eb2f1d-57a7-49c0-b381-94133435b6fa)

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/d5bde122-15b6-462f-81d3-871bc97c5389)


## Creación de pull requests

Visualice el repositorio remoto de destino en su navegador.<br>
Se ha subido un nuevo branch y aparece el botón "Compare & pull request".Haga clic en ese botón.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e3c2ac95-58b2-4bc6-b2cf-7c6c6a2ff216)

Aparece la siguiente pantalla.

①Branch de destino：El branch en la que se fusionará el pull request.<br>
②Banch de destino：El branch que se fusionará.

Una vez que haya introducido el contenido adecuado, haga clic en el botón `Create pull request` para crear la pull request.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a58ecd2a-184b-45f4-95bd-4fa138ad35cb)

Tras la creación, aparece la siguiente pantalla, que le permite comprobar el contenido.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/1be1f8eb-42e9-49bc-a6d5-744a2c1ace16)

## Revisar y fusionar

### Comprobación y revisión de las diferencias en el navegador.

Las revisiones pueden consultarse en la pestaña `Files changed` para ver los cambios realizados.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/215ab4a5-c9d8-45f3-a3f7-e3eb59577add)

Puede comentar el código si hay áreas que le gustaría que se corrigieran.<br>
Haga clic en el botón más que aparece en la fila de destino al pasar el ratón por encima.

Introduzca los datos que desea corregir y pulse el botón "Add single comment".

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e59db32f-e876-44c2-9996-0cbfdcd5abd5)

Los comentarios que introduzcas se incrustan en línea en el código fuente y también se transcriben en la pestaña "Conversación".

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/95b4e28e-2ac1-4cf1-bd1c-f5fd861153ef)

### Reflexión sobre el contenido de la revisión

Modifica el código según la revisión. <br>
Localmente, corrige la línea 3 en `sort.js`. El código modificado es el siguiente.

```
var sortNumber = function (number) {
   number.sort(function (a, b) {
       if (a === b) {
           return 0;
       }
       return a < b ? -1 : 1;
   });
};

var number = [19, 3, 81, 1, 24, 21];
sortNumber(number);
console.log(number);
```

Una vez modificado, ejecute commit y push de nuevo.

```
$ git add sort.js
$ git commit -m "Corregido el uso del operador de equivalencia estricta (===)"
$ git push origin add-sort-func
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/5b7f5522-3146-4073-b77d-bfabe8d209cc)

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/b3841c0d-0eb3-4e86-be52-b7b23c435867)

Comente el pull request que acaba de crear para informarles de que ha realizado una modificación.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6826ed6e-f498-468d-9d3d-b1aa3e8dbc31)

Desde la pestaña `Commits`, puede ver los cambios por commit. <br>
La pestaña `Files Changed` también muestra el diff con todos los commits incluidos.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/34af8b79-17d8-48dd-ba74-b15b0a2fbda4)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c2706c85-6b81-4fea-acd8-139635fb481c)

## Fusionar pull request en GitHub

Si la revisión no muestra problemas, fusione. Haz clic en el botón `Merge pull request` de la pestaña `Conversation`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c50d6d24-ca42-4ba1-a946-622b10d4cce4)

Aparecerán los siguientes botones. Haga los comentarios oportunos y pulse `Confirm merge` para proceder a la fusión.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a15fc17b-0f48-4003-b556-7c7d433695f0)

Una vez fusionadas, verá la siguiente pantalla.<br>
Aparecerá el botón `Delete branch`. Desde aquí puede eliminar los branches de tena que ya no sean necesarias.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/260c7251-4d32-4e01-ac71-8eb74d96712d)

La pestaña `Network` del menú `Insights` muestra que el `add-sort-func` se ha fusionado con el `master`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/f01f54d1-0f25-416f-8bb0-cb25de4ab05d)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e0a917fc-47ae-4776-92d2-e27d9f265652)

## Qué hacer en caso de conflicto

Hay casos en los que se producen conflictos de código y no pueden fusionarse automáticamente.<br>
Por ejemplo, pueden producirse conflictos en casos como el que se ilustra a continuación.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/dff8cc57-d954-4079-afe8-7c7f7eb3508b)

Cuando te enfrentas a una situación de conflicto por primera vez, puede ser difícil saber cómo responder.<br> 
Se necesita un poco de preparación para crear una situación de conflicto, pero vamos a experimentarla aquí.

### 1. Crea el primer commit y realiza un push al repositorio remoto

Primero, acceda a github e inicie sesión.
![https://github.com/](https://github.com/)

Haga clic en `el icono +` > `New repository`.

Introduzca el "Repository", seleccione acceso `Private` y pulse el botón `Create repository`. <br>
Aquí, introduje `pull-request-conflicto` en el nombre.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/95501772-656e-49e4-8e44-407155bad696)

Siga los siguientes comandos en Git Bash, cree un repositorio local llamado `pull-request-conflicto` y un archivo llamado `sort.js` y realize el primer commit. <br>
Para el contenido de `sort.js`, introduzca lo siguiente.

```
var number = [19, 3, 81, 1, 24, 21];
console.log(number);
```

〇Lista de comandos
```
$ mkdir ~/pull-request-conflicto
$ cd ~/pull-request-conflicto
$ git init
$ nano sort.js
$ cat sort.js
$ git add sort.js
$ git status
$ git commit -m "first commit"
$ git status
$ git log
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/dd56b40e-823c-4e0f-ba02-905c20ca8862)


Ejecute el siguiente comando para registrar la URL del repositorio remoto creado en la página anterior con el nombre origin.<br>
El segundo comando es para comprobar que se ha registrado.<br>
El tercer comando es para realizar un push contra el repositorio remoto origin.

Si especifica -u como opción, puede omitir especificar el nombre de la rama la próxima vez.
Sin embargo, al hacer push contra el primer repositorio remoto vacío, no puede omitir el nombre del repositorio remoto o el nombre del branch.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6b23803f-c0e5-4475-93e9-c70d2f523dba)

```
$ git remote add origin ★¡Pegue su propia url!★
$ git remote -v
$ git push -u origin master
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/61e23a62-e5e7-4a7e-b8e8-b3c7931c0331)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/76a3e25f-c63b-41d1-ba33-01c61cd6b6bb)


### 2. Crear branch de trabajo

Crea dos branches de trabajo.<br>
Un branch utiliza el operador de equivalencia (==) y el otro el operador de equivalencia estricta (===), lo que provoca un conflicto.

```
$ git checkout -b add-sort-func2
$ git checkout -b add-sort-func1
```

### 3. Editar el código en el branch add-sort-func1 y ejecutar un push.

En `add-sort-func1`, edita el código como sigue.

```
var sortNumber = function (number) {
   number.sort(function (a, b) {
       if (a === b) {
           return 0;
       }
       return a < b ? -1 : 1;
   });
};

var number = [19, 3, 81, 1, 24, 21];
sortNumber(number);
console.log(number);
```

Ejecute commit y push cuando la modificación se haya completado.

```
$ git diff
$ git add sort.js
$ git status
$ git commit -m "Añadido proceso para ordenar matrices"
$ git log
$ git push origin add-sort-func1
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/80ae9ade-835b-48fa-9d18-b70078bc436f)

### 4. Crear y fusionar un pull request para el branch add-sort-func1

En la pantalla de GitHub, crea una pull request y fusiónala.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/0c443cd2-a101-49a4-be80-fdde06f37b99)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ca2b25ae-fdf8-4fc6-b6ad-996c6edeaf0e)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/57ed933b-5755-4b42-bdcd-9b4a97224d84)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9d496f73-504e-49f1-a694-792a2633183b)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/1ba48102-d9f7-47dd-8e3e-a28681e5c0a9)

### 5. Editar el código en el branch add-sort-func2 y ejecutar un push.

Cambiar branch a `add-sort-func2`.

```
$ git checkout add-sort-func2
```

En `add-sort-func2`, edita el código como sigue.

```
var sortNumber = function (number) {
   number.sort(function (a, b) {
       if (a == b) {
           return 0;
       }
       return a < b ? -1 : 1;
   });
};

var number = [19, 3, 81, 1, 24, 21];
sortNumber(number);
console.log(number);
```

Ejecute commit y push cuando la modificación se haya completado.

```
$ git diff
$ git add sort.js
$ git status
$ git commit -m "Añadido proceso para ordenar matrices"
$ git log
$ git push origin add-sort-func2
```

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac5c9c1b-de0a-4b17-8140-a1c833880b36)

### 6. Crear un pull request para el branch add-sort-func2

En la pantalla de GitHub, crea una pull request.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6b2ee939-7b73-4a2b-bf95-d67047a89c53)

Se producen conflictos y no pueden fusionarse.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/86873e5a-325f-4156-a16c-b702f965379e)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/22abde12-a64c-48b0-b679-988d12fe6706)

## Resolución de conflictos.

Si surgen conflictos, edite y fusione el código manualmente.

### 1. Ejecutar un pull hacia el branch master.

En primer lugar, en el branch en el que está trabajando, ejecuta un pull hacia el branch destino de la `pull request`.<br>
De este modo, los últimos cambios en el branch de destino de la `pull request` se incorporan a el branch de trabajo.

En este caso, en `add-sort-func2` ejecutará un pull hacia `master`.

```
$ git branch
$ git pull origin master
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/71a740f4-78e3-4fab-a33d-4f626713edab)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e3195c4e-2b83-4851-98ce-94615e958a71)

### 2. Resolver los conflictos en el repositorio local.

Tras ejecutar el comando pull, se produce un conflicto local. Compruébalo con los siguientes comandos.

```
$ git branch
$ git pull origin master
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6e2f6f41-a782-4745-a822-7c7bd8ab3fd6)

Arriba `=======` es el código del repositorio local y abajo el código del repositorio remoto.<br>
En este caso, se elimina el código del repositorio local, quedando éste como está mejor en el repositorio remoto.<br>
El código editado es el siguiente.

```
var sortNumber = function (number) {
   number.sort(function (a, b) {
       if (a === b) {
           return 0;
       }
       return a < b ? -1 : 1;
   });
};

var number = [19, 3, 81, 1, 24, 21];
sortNumber(number);
console.log(number);
```

### 3. Vuelva a ejecutar commit y push después de modificar el código.

Ejecute los siguientes comandos para commit y push.

```
$ git add sort.js
$ git status
$ git commit -m "Resolución de conflictos."
$ git log
$ git push origin add-sort-func2
```

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2b4dff46-8eea-4188-9e59-36191fbf2cf4)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/cc38fce1-59b4-46d8-8546-1cd63ef2269d)

### 4. Confirme que el conflicto se ha resuelto en GitHub.

Si miras en la pantalla del pull request, el conflicto ha desaparecido y puedes fusionar.<br>
Ya puede fusionar como en el caso sin conflicto.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/99dd9388-45ed-4497-822f-5a96d9bddc2b)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/95d05d99-bd95-4c2c-9b0e-230f6e99477b)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/cf9b0499-a21a-4066-a8d1-895aad9470bd)

