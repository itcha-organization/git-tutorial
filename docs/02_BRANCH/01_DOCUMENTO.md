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

## Flujo ideal de trabajo con ***Branch***

![image](https://github.com/user-attachments/assets/abce21ca-15ec-4741-b33c-fd2c89bf12d7)

Branch `main` es un branch especial llamada `Base Branch` (Branch principal). Este branch se utiliza para mantener un estado estable que no contenga errores.
<br>
**No es deseable editar código y crear commit en el branch `main`, excepto para el primer commit.**

Antes de empezar a editar código, los miembros del equipo debería crear un branch dedicado a su propio trabajo a partir de el branch `main`, para trabajar sin afectar otros.<br>
A continuación, el miembro del equipo que ha terminado su trabajo incorpora los cambios de su propio branch al branch `main`.<br>

De este modo, el trabajo del miembro del equipo no se ve afectado por el trabajo de otros miembros del equipo y puede incorporarse a su propio trabajo.


¿Alguna vez ha tenido problemas para averiguar cuál es el último código justo antes de la presentación de un módulo?
Puede evitar esos problemas teniendo siempre el último código estable en el branch `main`.

## Integrar branch（merge）

Los branches de tema en los que se ha trabajado acaban fusionándose en el branch `main` utilizando un comando `merge`.

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

## conflicto

Cuando se ejecuta merge, las partes editadas del archivo se evalúan línea por línea y se fusionan automáticamente.

![image](https://github.com/user-attachments/assets/d93b6ad0-386d-477c-a745-6fe0bc25e8ee)

¿Qué ocurre si se realizan ediciones diferentes en la misma línea en cada branch, como se indica a continuación?

![image](https://github.com/user-attachments/assets/696a30b3-466d-40ee-afc2-2f0d161b25ab)

Si se modifica la misma línea en diferentes ramas, la fusión automática fallará.Esto se llama ***conflicto***.
<br>Para resolver el conflicto, debe modificar manualmente el archivo y crear un nuevo commit.

![image](https://github.com/user-attachments/assets/316ab0ec-35ca-4f7f-a361-95cfddb52ce6)
> [!NOTE]
>  ***Pasos para resolver conflictos:***
> 1. Mostrar archivos con conflicto con el commando `git status`
> 2. Abrir el archivo y corregir manualmente los conflictos
> 3. Agregar el archivo resuelto al staging con el commando `git add`
> 4. Completar el proceso con el commando `git commit`

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
