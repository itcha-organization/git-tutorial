# Compartir repositorios

## Realizar push a un repositorio remoto.

Hasta ahora, hemos descrito el uso básico de un repositorio local.<br>
Esta sección describe ahora cómo compartir el historial de cambios del repositorio local utilizando un repositorio remoto.

### Push

Para compartir el historial de cambios de su propio repositorio local en un repositorio remoto, necesita subir el historial de cambios en el repositorio local.

Para ello, Git realiza una operación llamada `Push`.<br>
Cuando realiza un `Push`, su historial de cambios se sube al repositorio remoto, de forma que el historial de cambios en el repositorio remoto es el mismo que el historial de cambios en el repositorio local.

> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/93ee162d-34c7-4a56-be7c-2ad54a0a098d)
> ![image](https://github.com/user-attachments/assets/db0fe0b1-c241-41e2-ae0b-f1d405a3a7f6)

## Clonar repositorios remotos.

Hasta esta sección, comenzamos nuestro trabajo creando un repositorio local vacío con `git init`.
<br>
Sin embargo, en el desarrollo en equipo real, es más común que cada miembro cree un repositorio local clonando un repositorio remoto común con `git clone`.

### Clone

Para duplicar un repositorio remoto, realice la operación `Clone`.

Cuando ejecuta clonar, puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local en otra máquina.

> [!NOTE]
>  El repositorio local clonado es también un duplicado del historial de cambios, por lo que puede consultar el historial y confirmar exactamente como lo hizo en el repositorio original.

## Realice un pull contra el repositorio remoto.

Cuando compartes un repositorio remoto y varias personas trabajan en él, todo el mundo realica un push al repositorio remoto.
A continuación, debe incorporar los cambios introducidos por los demás en su repositorio local.

### Pull

Para actualizar el repositorio local desde un repositorio remoto, utilice la operación `Pull`.

Ejecutando `Pull` descargará el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local. 

> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ef14dfa3-6d79-40fd-b0e8-aec3add6eada)
> ![image](https://github.com/user-attachments/assets/a0dd172e-9b2e-4c6e-81cc-3d7dd5095661)

## Incorporar los cambios con ***Pull Request*** en el repositorio remoto.

En el repositorio local, se utiliza `git merge` para incorporar los cambios del _branch de tema_ al _branch principal_(`main`).
<br>
En el repositorio remoto, se utiliza una función de GitHub llamada ***Pull Request*** para fusionar cambios al _branch principal_.

***Pull Request*** es una función de la interfaz gráfica de GitHub que le permite seleccionar el branch base y el branch que desea fusionar y realizar la fusión.

![image](https://github.com/user-attachments/assets/f7554e21-f3ee-4ee6-9c1d-239841b23b9e)

## ***GitHub Flow***: Flujo para un desarrollo en equipo eficiente utilizando GitHub

***GitHub Flow*** es una estrategia de trabajo con Git muy simple y popular, especialmente en proyectos que usan GitHub.

Con este flujo, puede disfrutar de las siguientes ventajas.
- Los procesos de trabajo se normalizan entre los miembros del equipo, lo que permite una cooperación más fluida.
- Branch `main` del repositorio remoto puede mantenerse actualizada y estable siempre.

![image](https://github.com/user-attachments/assets/89e3f427-ec4c-4003-844f-c09b54d60b70)
> **Pasos de GitHub Flow:**
> 1. En el repositorio local, actualizar `main` con `pull`. Si no hay repositorio local, clonar el repositorio remoto con `clone`.
> 2. En el repositorio local, crar un branch de trabajo a partir de `main`.
> 3. Codificar en el branch de trabajo.
> 4. Hacer un commit.
> 5. Subir el branch de trabajo al repositorio remoto con `push`.
> 6. Crear un pull request para fusionar el branch de trabajo en `main` en GitHub.
> 7. Fusionar el pull request en GitHub.
> 8. Eliminar el branch de trabajo fusionado en GitHub.
> 9. Eliminar el branch de trabajo fusionado en el repositorio local.

<details>

<summary>Más información: ¿Qué es Fetch?
</summary>

## Diferencias entre Pull y Fetch

El comando `fetch` para reflejar la última información del repositorio remoto en el repositorio local.<br>
Comprueba la diferencia entre el comando `pull` y el comando `fetch`.

### Pull

Puede ejecutar `pull` para obtener el historial del repositorio remoto. El siguiente diagrama ilustra lo que ocurre con las confirmaciones en el repositorio en este momento.

En primer lugar, veamos el caso en el que no se han realizado cambios en el branch del repositorio local que se está actualizando.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/733a8f5f-2030-4752-8894-6a6f2ebe5e43)

En este caso, simplemente se realiza un `fast-forward merge`. En el diagrama, `master` representa `branch master` en el repositorio local y `origin/master` representa `branch master` en el repositorio remoto `origin`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e27d5c77-3088-4cbe-804c-54adbc914af7)

Si también ha avanzado la historia en el repositorio local `branch master`, necesita fusionar ambos cambios. 

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/67752b0a-3870-4d5d-8f5f-01b1677b8bd8)

Por lo tanto, un `pull` resultará en un `merge`. En este momento, si no hay cambios conflictivos, se creará automáticamente un `merge commit`.<br> Sin embargo, si hay conflictos, debe resolverlos y luego crear el `commit` usted mismo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/57c69dff-d64a-4f8d-bb7e-cdfdf2086d13)

### Fetch

Cuando se realiza `pull`, el contenido del repositorio remoto se fusiona automáticamente.<br>
Sin embargo, hay ocasiones en las que simplemente quiere comprobar el contenido de un repositorio remoto y no quiere fusionar. En tales casos, utilice `fetch`.

Ejecutar `fetch` sólo recuperará el último historial del repositorio remoto.<br>
El `commit` recuperado se toma como un `branch` sin nombre. Puede cambiar a este `branch` especificando el nombre `FETCH_HEAD` en el comando `checkout`.

Por ejemplo, si se realiza un `fetch` con un `commit` que ha progresado desde `commit B` en cada uno de los `origin` de los repositorios local y remoto, el historial tendrá el aspecto de la figura siguiente.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/61b598c3-ac3b-46d8-ae88-ee2ccbf00bcf)

Desde este estado, si desea fusionar el contenido del repositorio remoto en el `master` del repositorio local, fusione `FETCH_HEAD` o ejecute `pull` de nuevo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2d52a6b2-85a9-458b-ba81-f41d1c58fb35)


> [!NOTE]
>  Cuando se realiza una fusión, el historial es el mismo que cuando se realiza un `pull`. En realidad, `pull` es porque está realizando `fetch` y `merge` internamente.

</details>
