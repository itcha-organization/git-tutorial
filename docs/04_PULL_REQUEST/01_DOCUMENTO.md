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

### El trabajo de revisión puede asignarse, gestionarse y registrarse

Las pull requests que se han creado pueden verse en una lista, lo que facilita la comprobación de las pull requests no completadas.<br>
Esto permite a los revisores procesar las pull requests creadas sin omisiones.

Los autores de pull requests y los revisores pueden intercambiar y discutir comentarios sobre los pull requests.<br>
Si es necesario, puede modificar codigos y ejectar commit y push tantas veces como quieras en el branch de destino.<br>
Cuando se ejecuta un push, el commit enviado se refleja automáticamente en el pull request.

La calidad del código fusionado final puede ser alta tras las interacciones anteriores.<br>
Estos intercambios también se registran en el servidor, de modo que los intercambios pasados puedan verse y discutirse de nuevo cuando surjan problemas.

### Puede facilitar las revisiones.

Un pull request puede mostrar claramente las partes modificadas del código.
El autor del pull request también puede comunicar la intención del código y cualquier información adicional en forma de comentarios. Esto reduce la carga del revisor.


## Proceso de desarrollo mediante pull requests.

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

