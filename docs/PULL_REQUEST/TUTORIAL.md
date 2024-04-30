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
