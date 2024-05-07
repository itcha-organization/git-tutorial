# Ejercicios de pull request

## Pregunta 1

Cree una carpeta `~/ejercicio4` y colócala bajo control Git.<br>
En el directorio `~/ejercicio4`, cree un archivo llamado `pull_request.txt` y haga commit.<br>
Luego compruebe el historia de commit.

## Pregunta 2

Ve a GitHub en su navegador y cree un repositorio privado, llamado `ejercicio4`.

## Pregunta 3

Registre el repositorio remoto `ejercicio4` creado en la pregunta 2 como remoto del repositorio local `ejercicio4` usando comandos en GitBash.<br>
A continuación, realice un push para reflejar los cambios en el repositorio remoto.<br>
Luego, compruebe que el historial de commits y el archivo se han añadido en GitHub.

## Pregunta 4

Crea un branch `add_description_of_type_of_branch` y un branch `add_description_of_command` y muévale a el branch `add_description_of_type_of_branch`.<br>
Luego muestre la lista de branches.

## Pregunta 5

Añada el siguiente texto a `pull_request.txt` y ejecute commit.<br>
Ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio4`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.
```
Base Branch (Rama Base):
  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
Topic Branch (Rama de Tema):
  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.
```

## Pregunta 6

En GitHub, crea un pull request y fusiona los cambios de Pregunta 5 en el branch master.

## Pregunta 7

Ve a el branch llamado `add_description_of_command`.<br>
Añada el siguiente texto a `pull_request.txt` y ejecute commit.<br>
Ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio4`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.

```
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

## Pregunta 8

En GitHub, crea un pull request para fusiona los cambios de Pregunta 7 en el branch master.

## Pregunta 9

Los pull requests creados en Pregunta 8 no pueden fusionarse debido a un conflicto.<br>
Por favor, resuelva el conflicto y fusione el pull request.

___
### Consejos de pregunta 9
En primer lugar, en el branch en el que está trabajando, ejecuta un pull hacia el branch destino de la pull request.<br>
De este modo, los últimos cambios en el branch de destino de la pull request se incorporan a el branch de trabajo.

En segundo lugar, modifique el contenido del archivo para que los cambios realizados en ambas branches permanezcan.

En tercer lugar, ejecute commit y push cuando la modificación se haya completado.
___
