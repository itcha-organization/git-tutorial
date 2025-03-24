# Concepto de branch（rama）

## ¿Qué es Branch (rama)?

En el desarrollo de software, varios miembros de un equipo pueden estar añadiendo características o corrigiendo errores en una misma pieza de software al mismo tiempo.<br>
Para ayudar con estos cambios de código paralelos, Git tiene una función llamada branch (rama).

Branch es una función de Git para ramificar la historia de un repositorio para trabajar de forma independiente.
<br>
Los branches no se ven afectadas por otros branches, por lo que se pueden realizar múltiples tareas en paralelo, como desarrollar nuevas funciones y corregir errores, mientras se mantiene la historia principal de desarrollo (branch `main`).

> ![image](https://github.com/user-attachments/assets/9a2fbf3d-e0f5-4472-a8db-347ac6cede8d)

Imagine las siguientes situaciones. ¿Sería útil un branch que permitiera trabajar en paralelo?

* Al dividir el trabajo entre los miembros del equipo
* Al solucionar un error urgente intrusivamente
* Cuando quiera experimentar con un cambio temporal en un fragmento de código

En Git, es habitual utilizar dos tipos de Branch, `Base Branch` y `Topic Branch`, para conseguir un trabajo paralelo.

* `Base Branch` (Branch principal)<br>
  Este branch se utiliza para mantener un estado estable que no contenga errores. Normalmente, trata la branch `main` como branch principal.

* `Topic Branch` (Branch de Tema)<br>
  Un topic branch es un branch que se crea para trabajar en un tema, como desarrollar nuevas funciones y corregir errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en el y se integra en el base branch.

El diagrama siguiente ilustra el trabajo paralelo mediante branch.

> ![image](https://github.com/user-attachments/assets/0c7f6ae6-0d3a-4d3c-bb34-c6e1ded31299)

Los miembros del equipo crean un branch dedicado a su propio trabajo a partir de el branch principal, de modo que su trabajo no se vea afectado por el de otros miembros del equipo.<br>
A continuación, el miembro del equipo que ha terminado su trabajo incorpora los cambios de su propio branch al branch principal.<br>
De este modo, el trabajo del miembro del equipo no se ve afectado por el trabajo de otros miembros del equipo y puede incorporarse a su propio trabajo.

## Integrar branch（merge）

Los branches de tema en los que se ha trabajado acaban fusionándose en un branch principal utilizando un comando `merge`.

### merge

`merge` puede utilizarse para fusionar varios flujos de historial.

Por ejemplo, supongamos que tiene un branch llamada `bugfix` que se ramifica a partir de el branch `main`, como se muestra en el siguiente diagrama. 

![image](https://github.com/user-attachments/assets/19526091-2026-4ae1-89ef-47b8eb596652)

En este caso, para incorporar correcciones del branch `bugfix` al branch `main`, los cambios en ambos `main` y los cambios en el `bugfix` necesitan ser combinados en uno.
<br>Por lo tanto, se crea un commit de fusión que incorpora ambos cambios. El puntero del `main` se traslada a ese _commit_.
<br>Los commits creados por `merge`, como este commit, se llaman ***merge commit***.

![image](https://github.com/user-attachments/assets/c9e4398d-7b94-44ae-a2d7-06afba095e91)

#### Fast-Forward Merge

Cuando las dos ramas se fusionan, se crea un nuevo ***merge commit***.
<br>Sin embargo, si no se crea un nuevo commit en el lado `main` después de que `bugfix` se ramifique desde `main`, como se muestra a continuación, no se creará ningún ***merge commit***.

![image](https://github.com/user-attachments/assets/23d31582-9d93-4a2f-9532-255a957e41d7)

La ejecución de merge simplemente mueve el puntero de `main` a la posición del `bugfix` para incorporar correcciones del branch `bugfix` al branch `main`.
Una fusión en la que no se crea un ***merge commit*** se denomina ***fast-forward merge*** (fusión rápida).

![image](https://github.com/user-attachments/assets/ef270ef4-96e6-41c4-bdeb-ccb456aca668)

<details>

<summary>Ejemplo práctico de operación con `Topic Branch` y `Base Branch`
</summary>

## Ejemplo práctico de operación con `Topic Branch` y `Base Branch`

El funcionamiento con `Topic Branch` y `Base Branch` se ilustra con un sencillo ejemplo.

Por ejemplo, supongamos que está trabajando en el topic branch añadiendo una función y tiene que corregir un error.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8924bf8c-2f0a-4eb3-9e22-89097b01d0e5)

En estos casos, la `Base Branch` está todavía antes del desarrollo de la característica, por lo que se puede empezar a trabajar independientemente del desarrollo de la función nueva creando un nuevo `Topic Branch` para la corrección de errores desde aquí.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8c2c38e8-2a2d-4b7b-9d8c-d5b86704e48b)

Las correcciones de errores completadas pueden publicarse incorporándolas a la `Base Branch` original.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/67f3d725-5486-42e8-835e-6472ef165b34)

A continuación, puede volver a el _branch_ original `azul` para seguir desarrollando la función.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/46ad66ca-c4e7-4674-ad46-0827cfb9a3ca)

Sin embargo, le dio cuenta de que necesitaba el contenido de la corrección de errores actual, `commit X`, para continuar el trabajo.<br>
Aquí, hay dos maneras de importar el contenido de `commit X`: usando `merge` o `rebase`.　En este caso, hemos decidido utilizar `rebase` para integrar los cambios en la `Base Branch`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/94d99577-54bf-409f-a602-671b7a7a93c5)

Esto le permite continuar desarrollando la función con el contenido de `commit X` incorporado. De este modo, la bifurcación les permite trabajar en diferentes tareas en paralelo.

</details>
