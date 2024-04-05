# Concepto de branch（rama）

## ¿Qué es Branch?

En el desarrollo de software, varios miembros de un equipo pueden estar añadiendo características o corrigiendo errores en una misma pieza de software al mismo tiempo.<br>
Para ayudar con estos cambios de código paralelos, Git tiene una función llamada ramificación.

Las ramas se utilizan para bifurcar y registrar el flujo de la historia.<br>
Las ramas no se ven afectadas por otras ramas, por lo que se pueden realizar múltiples cambios al mismo tiempo en el mismo repositorio.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/92c0e870-645b-45fd-8e23-a72aaa5aa3b5)

Imagine las siguientes situaciones. ¿Sería útil una rama que permitiera trabajar en paralelo?

* Al dividir el trabajo entre los miembros del equipo
* Al solucionar un error urgente intrusivamente
* Cuando quiera experimentar con un cambio temporal en un fragmento de código

El diagrama siguiente ilustra el trabajo paralelo mediante ramas.

Los miembros del equipo crean una rama dedicada a su propio trabajo a partir de la rama principal, de modo que su trabajo no se vea afectado por el de otros miembros del equipo.<br>
A continuación, el miembro del equipo que ha terminado su trabajo incorpora los cambios de su propia rama a la rama principal.<br>
De este modo, el trabajo del miembro del equipo no se ve afectado por el trabajo de otros miembros del equipo y puede incorporarse a su propio trabajo.<br>
Esto también facilita la investigación y resolución de cualquier problema que pueda haber surgido.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ab94fccc-d3e4-4a32-8044-e9c76c942cd9)


