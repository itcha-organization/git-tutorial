# EJERCICIO

## Pregunta 1

Cree una carpeta `~/ejercicio2` y colócala bajo control Git.

## Pregunta 2

En el directorio `~/ejercicio2`, cree un archivo llamado `resumen_de_branch.txt` y haga commit.<br>
En el contenido del archivo, introduzca el siguiente texto.
Compruebe el historia de commit.
```
Resumen de branch
```

## Pregunta 3

Crea un branch `add_description_of_type_of_branch` y un branch `add_description_of_command` y muévale a el branch `add_description_of_type_of_branch`.<br>
Luego muestre la lista de branches.

## Pregunta 4

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.
```
Base Branch (Rama Base):
  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
Topic Branch (Rama de Tema):
  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.
```

## Pregunta 5

Ve a el branch llamado `add_description_of_command`.<br>
Luego muestre la lista de branches.

## Pregunta 6

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.

```
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

## Pregunta 7

Fusiona los cambios realizados en `add_description_of_type_of_branch` en el `master`.<br>
Ve a `master` y luego importa `add_description_of_type_of_branch` usando comando `merge`.

## Pregunta 8

Fusiona los cambios realizados en `add_description_of_command` en el `master`.

Importa la `add_description_of_command` usando comando `merge` también.<br>
En caso de conflicto, modifique el contenido del archivo para que los cambios realizados en ambas branches permanezcan.

## Pregunta 9

Elimine `add_description_of_type_of_branch` y `add_description_of_command`.<br>
Luego muestre la lista de branches.
