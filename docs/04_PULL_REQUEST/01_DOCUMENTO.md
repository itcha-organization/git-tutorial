# Pull request

En el repositorio local, se utiliza `git merge` para incorporar los cambios del _branch de tema_ al _branch principal_(`main`).
<br>
En el repositorio remoto, se utiliza una función de GitHub llamada ***Pull Request*** para incorporar cambios al _branch principal_.

## ¿Qué es ***Pull Request*** ?

`Pull Request` (a menudo denominada `PR`) es una propuesta para fusionar un conjunto de cambios de una rama en otra.

`Pull Request` proporciona una representación visual de las diferencias de contenido entre el branch de origen y el branch de destino.
<br>
Por eso, al crear un `Pull Request`, se puede revisar un conjunto de cambios con otros miembros antes de que se incorporen al código base principal. 

`Pull Request` facilita la revisión del código dentro del equipo y contribuye a la detección temprana de errores

![image](https://github.com/user-attachments/assets/783aff74-a220-49d2-936b-ec7462748b21)

## Ventajas de los pull requests

### Se puede encontrar errores al revisar la lista de cambios
- Al revisar la lista de archivos modificados, puedes verificar si falta algún archivo o si se ha añadido uno por error.
- Al revisar los cambios en el código, puedes detectar errores tipográficos o pequeños errores de implementación.

### Registro del historial de cambios e intenciones
- Usando el título, la descripción y los comentarios, puedes incluir información de contexto sobre "por qué se realizaron estos cambios".
- En el futuro, si alguien necesita saber la razón de un cambio, podrá consultar la información en el Pull Request.

## Pasos para resolver conflicto y actualizar `Pull Request`
Si el branch de trabajo a fusionar está en conflicto con el branch `main`, se puede crear una Pull Request, pero no se puede fusionar tal cual.
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/86873e5a-325f-4156-a16c-b702f965379e)
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/22abde12-a64c-48b0-b679-988d12fe6706)

### 1. Ejecutar un pull hacia el branch main de remote.
En primer lugar, en el branch en el que está trabajando, ejecuta un pull hacia el branch de base de la `pull request`.<br>
De este modo, los últimos cambios en el branch de base de la `pull request` se incorporan al branch de trabajo.
```
git checkout ★nombre de branch de trabajo★
```
```
git pull origin main
```

### 2. Resolver los conflictos en el repositorio local.
Tras ejecutar el comando pull, se produce un conflicto local. Compruébalo con el comandos `git status`.
<br>
Abra el archivos con conflict y resuelva los conflictos manualmente. (El procedimiento es el mismo que el aprendido en el tema de branch.)

### 3. Vuelva a ejecutar commit y push después de modificar el código.
Cree un commit y complete la resolución del conflicto.

A continuación, suba al mismo branch en el remoto y refleje la adición de commit en el branch remote.
<br>
Abra la pestaña `commit` de la `Pull Request` para ver que se ha actualizado.

![image](https://github.com/user-attachments/assets/fdd9c19d-ee9c-4baf-be7a-2dd87f7aa2a6)

## ⚡IMPORTANTE⚡ Estrategias para reducir los conflictos

### 1. **Crear Pull Requests pequeños y frecuentes**
- Los cambios grandes tienden a generar más conflictos.
- Si envías Pull Requests de **pequeña escala (por funcionalidad o por corrección específica)**, las revisiones serán más rápidas y las fusiones más sencillas.
- Lo ideal es **"un PR debe tener un solo propósito"**.

### 2. **Organizar bien la asignación de tareas**
- Cuando varias personas editan el mismo archivo frecuentemente, es más fácil que ocurran conflictos.
- Al momento de asignar las tareas, si se presta atención para reducir la edición de un mismo archivo por varias personas, se pueden evitar conflictos.

### 3. **Mantenerse actualizado con la rama `main`**
- Si actualizas periódicamente tu rama de trabajo local con `git pull origin main` para **mantener una base actualizada**, los conflictos serán menores y más fáciles de resolver.
- Es fundamental **incorporar los cambios de `main` antes de hacer un `push`**.

### 4. **Mantener una comunicación fluida con el equipo**
- Una comunicación constante y clara entre los miembros del equipo ayuda a prevenir conflictos antes de que ocurran.

<details>

<summary>Proceso de desarrollo con revisión de código
</summary>

## Proceso de desarrollo con revisión de código
El proceso mediante pull requests es el siguiente.

①[ Desarrollador ] Realice un clone o pull para obtener el código en el repositorio remoto con el que está trabajando.<br> 
②[ Desarrollador ] Crear un branch de trabajo en el repositorio local.<br>
③[ Desarrollador ] Modificar el código.<br>
④[ Desarrollador ] Cuando el trabajo esté terminado, realice un push.<br>
⑤[ Desarrollador ] Crear un pull request.<br>
⑥[ Encargado de la revisión ] Compruebe y revise los cambios de la pull request notificada.<br>
⑦[ Encargado de la revisión ] Determine los resultados de la revisión y proporcione información al desarrollador si es necesario.<br>
⑧[ Encargado de la revisión ] Si, tras la revisión, no hay problemas, fusiona.<br>
⑨[ Encargado de la revisión ] Si, como resultado de la revisión, la pull request en sí ya no es necesaria, por ejemplo, la respuesta en sí ya no es necesaria, la pull request se cierra.

Repita los pasos 3-7 anteriores tantas veces como sea necesario. Como resultado, se puede mejorar la calidad del código fusionado final.

![image](https://github.com/user-attachments/assets/ed9f61f7-1a61-4897-92ef-d912dd883842)

</details>
