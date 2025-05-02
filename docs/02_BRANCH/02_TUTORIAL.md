# Tutorial de Branch

En este tutorial, realizará cada una de las tres tareas siguientes en un branch de trabajo
- Tarea1: Añadir la línea de resumen del comando `checkout` a un archivo.
- Tarea2: Añadir la línea de resumen del comando `branch` a un archivo.
- Tarea3: Añadir la línea de resumen del comando `merge` a un archivo.

Para cada tarea, repetirás el siguiente flujo.
- Crear un branch.
- Editar el código según las instrucciones de la tarea y hacer un commit.
- Fusionar en el branch `main`

## REPASO: Crear un nuevo repositorio y un commit initial: init, add, commit

Primero, crea un nuevo directorio y crea un repositorio vacío en él. Aquí, hemos creado un directorio llamado `tutorial_branch`.
```
mkdir ~/tutorial_branch
```
```
cd ~/tutorial_branch
```
```
git init
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/52ea72f1-cf20-4195-9f87-2237d6cef2f3)

</details>

Ejecute el siguiente commando para abrir VS Code en el directorio actual.
```
code .
```
> ![image](https://github.com/user-attachments/assets/0a4eef33-048d-4717-93da-8724a543e5f1)

Cree un achivo de texto llamado `myfile.txt` en el directorio `tutorial_branch`.
<br>
Abra el archivo y pegue el siguiente texto y guárdelo.

```
Comandos Git para manejar branch
```
> ![image](https://github.com/user-attachments/assets/bf72a990-358f-4235-a56e-cb0baad3058c)

Haga un commit initial.
```
git add myfile.txt
```
```
git status
```
```
git commit -m "first commit"
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/8bcd6704-dff4-498b-8155-850ac359b1d9)

</details>

El historial de commit en este punto se parece a esto.

![image](https://github.com/user-attachments/assets/6c080e70-8f0c-4f04-bb6b-4b134ab0dacb)

> [!NOTE]
>  ***HEAD:***
> Es un puntero que indica dónde está trabajando actualmente, normalmente el commit más reciente en el extremo.

## Crear un branch: branch
Aquí, creamos un branch llamada `tarea1`.

Los branches pueden crearse con el comando `branch`. Es habitual utilizar el resúmen de la tarea como nombres de branch.
> ```
> $ git branch <nombre de branch>
> ```

Vamos a crear un branch llamada `tarea1`. 
```
git branch tarea1
```
Ejecute el comando `branch` sin parámetros para ver una lista de branch. El branch con el prefijo * es el branch actual.
```
git branch
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/cc404541-bd07-400b-8c88-3bc472c05ec6)

</details>

El historial de commit en este punto se parece a esto.

![image](https://github.com/user-attachments/assets/39c9e346-cfb2-4433-9797-0a37ebe31048)

## Cambiar el branch actual: checkout

Para añadir _commits_ a su branch `tarea1` recién creada, necesita cambiar el branch actual a `tarea1`.

El cambio de branch se realiza con el comando `checkout`.
> ```
> $ git checkout <nombre de branch>
> ```
Cambie a el branch `tarea1`.<br>
A continuación, utilice el comando `git branch` para confirmar que el branch actual ha pasado al `tarea1`.
```
git checkout tarea1
```
```
git branch
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/ee6494d8-9699-4816-9c72-a9ed0a94149f)

</details>

El historial de commit en este punto se parece a esto.

![image](https://github.com/user-attachments/assets/546a529a-0a2f-4dce-9cd1-a5f7bc84ef31)

> [!NOTE]
> El comando `checkout` con la opción `-b` **crea branch nuevo y cambia de branch a la vez**. En realidad, este comando se utiliza más.
> ```
> $ git checkout -b <nombre de branch>
> ```

Si ejecutas commit mientras el branch actual es `tarea1`, el commit se registrará en `tarea1`.

Añada la siguiente descripción del comando checkout al archivo `myfile.txt` y guárdelo.
```
Checkout: Cambia o Crea Branch
```
> ![image](https://github.com/user-attachments/assets/7b29c449-9071-4e49-8847-25110e79084f)

En Git bash, haga un commit
```
git add myfile.txt
```
```
git status
```
```
git commit -m "Se ha añadido la descripción de la Checkout"
```
```
git log
```

El historial de commit en este punto se parece a esto.

![image](https://github.com/user-attachments/assets/f8f72d55-1408-4bf5-9231-e8438b469b10)

## Integrar Branches y Funcionalidades: merge

Fusiona los cambios realizados en el branch `tarea1` en el branch `main`.

Para realizar la fusión entre ramas usamos el comando `merge`.
<br>
Tenemos que hacerlo estando situados en el branch que queremos usar como base, e indicando el nombre del branch que queremos fusionar.
> ```
> $ git merge <nombre de branch que queremos fusionar>
> ```

En este caso, para fusionar `tarea1` en `main`, primero ve a `main`.
```
git checkout main
```

Antes de ejecutar `merge`, compruebe el historial de cambios del repositorio usando la comando `git log`.
<br>
En `main`, el historial contiene solo initial commit.
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/115cb39a-d311-4682-beb6-9177e3180577)

</details>

Antes de ejecutar `merge`, abra `myfile.txt` en VS Code.
El archivo se editó en `tarea1`, por lo que el contenido de `myfile.txt` en `main` no se ha modificado.
<br>
Branch le permite **cambiar entre diferentes versiones de código al instante**.
> ![image](https://github.com/user-attachments/assets/1ddea53e-a04b-431c-bf9b-9edce85e421e)

Ejecte `merge` para fusionar el branch `tarea1` en el branch `main`.
```
git merge tarea1
```

Compruebe el historial de cambios del repositorio usando la comando `git log`.<br>
Se ha añadido commit de "Se ha añadido la descripción de la Checkout".
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/983027ec-66d7-4687-84fe-344bdbf39245)

</details>

Abra `myfile.txt` para ver el contenido.
La segunda línea añadida en el branch `tarea1` ha sido incorporada al archivo en el branch `main`.
> ![image](https://github.com/user-attachments/assets/c08c0fb5-4a5a-4a8b-9368-683f132adb29)

En este ejemplo commit apuntado por `main` se ha movido a la misma posición que `tarea1` despues de merge.
Esta `merge` es un `fast-forward (avance rápido) merge`.

![image](https://github.com/user-attachments/assets/b74fd88b-7e7a-4e3d-a859-115f6c24c5ba)

## Eliminar branch: branch -d
El contenido de `tarea1` se ha fusionado con éxito en `main` y debería eliminarse. Para eliminar un branch, ejecute el comando `branch` con la opción `-d`.
> ```
> $ git branch -d <nombre de branch>
> ```

Para eliminar `tarea1`, ejecte el siguiente comando.
```
git branch -d tarea1
```

Ahora `tarea1` ha sido eliminado. Utilice el comando `branch` para ver si el branch ha sido eliminada.
```
git branch
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/758ab5fe-7a2c-45ea-aa54-74e88fd057f8)

</details>

El historial de commit en este punto se parece a esto.

![image](https://github.com/user-attachments/assets/cea9b415-7d5b-405c-82ee-362b8aa8d19e)

## Trabajar en paralelo usando branches
A continuación, cree dos branches y trabaje en paralelo.

Primero, crea `tarea2` y `tarea3` y muévele a `tarea2`.
```
git branch tarea2
```
```
git branch tarea3
```
```
git checkout tarea2
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/35f4ba3d-7e9b-4046-82f4-a8d599f25750)

</details>

![image](https://github.com/user-attachments/assets/5ccad91b-d695-48e3-b125-a85cdb61614a)

Añada la siguiente descripción del comando branch al archivo `myfile.txt` y guárdelo.
```
Branch: Crear, eliminar branch o ver una lista de branch
```
> ![image](https://github.com/user-attachments/assets/f773fc5e-dc74-450f-b23a-cbd234b0db2f)

Haga commit.

```
git add myfile.txt
```
```
git status
```
```
git commit -m "Se ha añadido la descripción de Branch"
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/1ab26405-7448-4f73-85f9-c5a322f06b21)

</details>

![image](https://github.com/user-attachments/assets/336e1fa1-78cb-462a-b689-917b52f6415c)

Luego pasa al `tarea3`.
```
git checkout tarea3
```

Abra `myfile.txt`. La descripción del comando `branch` se añadido en `tarea2`, por lo que el `myfile.txt` en `tarea3` sólo tiene la descripción del comando `checkout`.

Añada la siguiente descripción del comando `merge` al archivo `myfile.txt` y guárdelo.
```
Merge: Integrar branch
```
> ![image](https://github.com/user-attachments/assets/7db589f3-b939-4540-87a7-41fde98a7c86)

```
git add myfile.txt
```
```
git status
```
```
git commit -m "Se ha añadido la descripción de Merge"
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/894d6ff1-8d12-4260-89de-e79668addafa)

</details>

![image](https://github.com/user-attachments/assets/2ad91927-fe15-46bc-8c9b-5d686c6183f6)

El trabajo para añadir la descripción de `branch` y la descripción de `merge` podría realizarse por separado.

## Resolución de conflictos en el merge

Los cambios realizados en `tarea2` y en `tarea3` deben fusionarse en `main`.

Primero, fusione `tarea2` en `main`.
Porque `main` es la base de la fusión, pase a `main` y luego fusione `tarea2` en `main`.
<br>
Luego con el commando `log`, compruebe que el commit realizado en `tarea2` se ha añadido al historial de commit en `main`.
```
git checkout main
```
```
git merge tarea2
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/b36fc9f6-28af-4077-8f4b-e8017eaaec6a)

</details>

Esta `merge` es un `fast-forward (avance rápido) merge`.

![image](https://github.com/user-attachments/assets/108136c2-0d5a-461a-973b-87797fd5ec63)

A continuación, fusione `tarea3` en `main` y compruebe que el commit realizado en `tarea3` se ha añadido al historial de commit en `main`.
```
git merge tarea3
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/99585dad-a802-4cf0-a145-cbcf673991f5)

</details>

Como resultado de `log`, no se ha capturado ningún commit, el `merge` automática ha fallado.
<br>
El conflicto se ha producido porque la tercera línea de `myfile.txt` se ha modificado en ambas branches `tarea2` y `tarea3`.

Abra `myfile.txt` y mire las filas en conflicto.
> ![image](https://github.com/user-attachments/assets/83be745f-b6f8-4728-b8d4-7f084b48cf44)

En caso de conflicto, debe corregirse manualmente al código correcto.<br>
Esta vez, tanto la descripción de `Branch` como la de `Merge` deben mantenerse, así que modifíquelas como sigue.<br>
**Para el desarrollo real, es mejor consultar con el equipo cómo corregir el problema correctamente.**

```
Comandos Git para manejar branch
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

Ahora que el conflicto se ha corregido, ejecute `commit` de nuevo.

```
git status
```
```
git add myfile.txt
```
```
git commit -m "He solucionado el conflicto entre las ramas tarea3 y main"
```
```
git log
```
<details>

<summary>Ejemplo de ejecución de comandos
</summary>

> ![image](https://github.com/user-attachments/assets/1856b2c6-eaa7-4623-8712-aeb2f742c781)

</details>

La historia es la siguiente.<br>
Esta _merge_ soluciona un conflicto, por lo que se ha creado un nuevo _merge commit_ para registrar el cambio. La cabecera de `main` se ha movido allí.<br>
Un _merge_ de este tipo se denomina _non fast-forward merge_.

![image](https://github.com/user-attachments/assets/f56ebcac-85b3-4472-8242-4d2ec4a1e883)

> [!NOTE]
>  ***HEAD:***
> Es un puntero que indica dónde está trabajando actualmente, normalmente el commit más reciente en el extremo.
