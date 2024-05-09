# Concepto de branch（rama）

## ¿Qué es Branch?

En el desarrollo de software, varios miembros de un equipo pueden estar añadiendo características o corrigiendo errores en una misma pieza de software al mismo tiempo.<br>
Para ayudar con estos cambios de código paralelos, Git tiene una función llamada branch (rama).

Los branches se utilizan para bifurcar y registrar el flujo de la historia.<br>
Los branches no se ven afectadas por otros branches, por lo que se pueden realizar múltiples cambios al mismo tiempo en el mismo repositorio.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/92c0e870-645b-45fd-8e23-a72aaa5aa3b5)

Imagine las siguientes situaciones. ¿Sería útil un branch que permitiera trabajar en paralelo?

* Al dividir el trabajo entre los miembros del equipo
* Al solucionar un error urgente intrusivamente
* Cuando quiera experimentar con un cambio temporal en un fragmento de código

El diagrama siguiente ilustra el trabajo paralelo mediante branch.

Los miembros del equipo crean un branch dedicado a su propio trabajo a partir de el branch principal, de modo que su trabajo no se vea afectado por el de otros miembros del equipo.<br>
A continuación, el miembro del equipo que ha terminado su trabajo incorpora los cambios de su propio branch al branch principal.<br>
De este modo, el trabajo del miembro del equipo no se ve afectado por el trabajo de otros miembros del equipo y puede incorporarse a su propio trabajo.<br>
Esto también facilita la investigación y resolución de cualquier problema que pueda haber surgido.

En Git, puedes crear branch a voluntad. Sin embargo, para utilizar branch de forma eficaz, es importante establecer de antemano reglas para su funcionamiento.

Las dos formas principales de operar con branch son la `Bese Branch` (Rama Base) y la `Topic Branch` (Rama de Tema).

* `Base Branch` (Rama Base)

Este branch se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en el y se integra en el base branch.

Normalmente, `master` branch o `main` branch se utiliza como base branch.

* `Topic Branch` (Rama de Tema)

Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e9298201-eb67-474f-8916-b486b33fa5c1)

## Integrar branch（merge, rebase）

Los branches de tema en los que se ha trabajado acaban fusionándose en un branch base. Hay dos formas de fusionar branches: utilizando `merge` o utilizando `rebase`. La historia de el branch fusionado difiere mucho según el método que se utilice.

### merge

`merge` puede utilizarse para fusionar varios flujos de historial.

Por ejemplo, supongamos que tiene un branch llamada `bugfix` que se ramifica a partir de el branch `master`, como se muestra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/161e54f6-c82c-45ed-ae11-65d38f12c7aa)

Fusionar este `bugfix` en `master` es muy fácil si el estado de `master` no ha cambiado desde antes. El historial de `bugfix` contiene todo el historial de `master`, por lo que `master` puede simplemente pasar a incorporar el contenido de `bugfix`. Este tipo de _merge_ se denomina _fast-forward (avance rápido) merge_.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/855eba0c-f18c-49cb-ab5f-76c6929ece49)

Sin embargo, hay casos en los que la historia del `master` ha avanzado más que cuando se bifurcó el `bugfix`. En este caso, los cambios en ambos `master`s y los cambios en el `bugfix` necesitan ser combinados en uno.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8df4c7d8-656d-4b5a-a4d7-9fbec317e16d)

Por lo tanto, se crea un _merge commit_ de fusión que incorpora ambos cambios. La cabecera del `master` se traslada a ese _commit_.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/f26feea3-2580-40f3-adc3-635b10196c94)

### rebase

Como en el ejemplo `merge`, supongamos que hay una rama llamada `bugfix` que parte de `master`, como se muestra en el diagrama de abajo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/45b061d2-2b94-43c8-9f45-30aad225dace)

Si fusionas los branches usando `rebase`, la historia se parecerá al diagrama de abajo.

Cunado usione `bugfixes` en `master` usando `rebase`, la historia de `bugfix` se sustituye después de `master`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2a8d5574-b01c-40ef-a1b9-d70baf6f5a22)

Se recomienda utilizar el comando `merge` si no está familiarizado con Git.

## Ejemplo de operación con `Topic Branch` y `Base Branch`

El funcionamiento con `Topic Branch` y `Base Branch` se ilustra con un sencillo ejemplo.

Por ejemplo, supongamos que está trabajando en el topic branch añadiendo una función y tiene que corregir un error.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8924bf8c-2f0a-4eb3-9e22-89097b01d0e5)

En estos casos, la `Base Branch` está todavía antes del desarrollo de la característica, por lo que se puede empezar a trabajar independientemente del desarrollo de la característica creando un nuevo `Topic Branch` para la corrección de errores desde aquí.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/8c2c38e8-2a2d-4b7b-9d8c-d5b86704e48b)

Las correcciones de errores completadas pueden publicarse incorporándolas a la `Base Branch` original.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/67f3d725-5486-42e8-835e-6472ef165b34)

A continuación, puede volver a el _branch_ original `azul` para seguir desarrollando la función.
![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/46ad66ca-c4e7-4674-ad46-0827cfb9a3ca)

Sin embargo, le dio cuenta de que necesitaba el contenido de la corrección de errores actual, `commit X`, para continuar el trabajo.<br>
Aquí, hay dos maneras de importar el contenido de `commit X`: usando `merge` o `rebase`.　En este caso, hemos decidido utilizar `rebase` para integrar los cambios en la `Base Branch`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/94d99577-54bf-409f-a602-671b7a7a93c5)

Esto le permite continuar desarrollando la función con el contenido de `commit X` incorporado. De este modo, la bifurcación les permite trabajar en diferentes tareas en paralelo.
