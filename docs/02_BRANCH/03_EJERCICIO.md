# EJERCICIO

Resuelva las preguntas 1-9 utilizando los comandos en GitBash.<br>
Para las preguntas 5~8, por favor ilustre el historial de commit en el siguiente archivo.

[BRANCH_EJERCICIO_ilustración_de_commit](https://docs.google.com/spreadsheets/d/1bg0ciGd_One_CkfUe4flF6XY6BAEG_zL/edit?usp=sharing&ouid=106974386879104420094&rtpof=true&sd=true)

## Pregunta 1

Cree una carpeta `~/ejercicio2` y colócala bajo control Git.

<details>
<summary>Ejemplo de respuesta</summary>

  ![image](https://github.com/user-attachments/assets/8e16a12f-f4ac-499f-954a-1b8b5bc2a835)

</details>

## Pregunta 2

En el directorio `~/ejercicio2`, cree un archivo llamado `resumen_de_branch.txt` y haga commit.<br>
En el contenido del archivo, introduzca el siguiente texto.
Compruebe el historia de commit.
```
Resumen de branch
```

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/b38b8f0c-4da9-428d-b966-d6692e12e3b0)

</details>

## Pregunta 3

Crea un branch `add_description_of_type_of_branch` y un branch `add_description_of_command` y muévale a el branch `add_description_of_type_of_branch`.<br>
Luego muestre la lista de branches.

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/3cfe1c6a-d74b-4cee-bf9c-b370363d7696)

</details>

## Pregunta 4

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.
```
Base Branch (Rama Base):
  Esta rama se utiliza para mantener un estado estable que no contenga errores. Cuando se realiza algún cambio, se crea un topic branch, se trabaja en ella y se integra en el base branch.
Topic Branch (Rama de Tema):
  Un topic branch es un branch que se crea para trabajar en un tema, como añadir una característica o corregir un error. Si está trabajando en varias temas al mismo tiempo, cree varias topic branches como necesite.
```

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/67bc38a2-7a66-4eb3-9439-599909ad09ad)

</details>

## Pregunta 5

Ve a el branch llamado `add_description_of_command`.<br>
Luego muestre la lista de branches.

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/1c898942-f8ee-49c7-938f-7c3271641821)

</details>

## Pregunta 6

Añada el siguiente texto a `resumen_de_branch.txt` y ejecute commit.
Compruebe el historia de commit.

```
Checkout: Cambia o Crea Branch
Branch: Crear, eliminar branch o ver una lista de branch
Merge: Integrar branch
```

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/3b30b1fa-28d1-4301-9297-1dce1eada5fb)

</details>

## Pregunta 7

Fusiona los cambios realizados en `add_description_of_type_of_branch` en el `main`.<br>
Ve a `main` y luego importa `add_description_of_type_of_branch` usando comando `merge`.

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/bdd87b1c-43e1-49cf-80aa-879d594c1ea8)

</details>

## Pregunta 8

Fusiona los cambios realizados en `add_description_of_command` en el `main`.

Importa la `add_description_of_command` usando comando `merge` también.<br>
En caso de conflicto, modifique el contenido del archivo para que los cambios realizados en ambas branches permanezcan.

<details>
<summary>Ejemplo de respuesta</summary>

  ![image](https://github.com/user-attachments/assets/e8ea6d92-75b7-4cfc-b466-15b06cb9a7e4) 
  
  ![image](https://github.com/user-attachments/assets/a46bbab9-13a6-4882-bc82-db6dc702d593)

</details>

## Pregunta 9

Elimine `add_description_of_type_of_branch` y `add_description_of_command`.<br>
Luego muestre la lista de branches.

<details>
<summary>Ejemplo de respuesta</summary>
  
  ![image](https://github.com/user-attachments/assets/2e454e5c-3bc3-4075-95a8-c8630ffb36bb)

</details>
