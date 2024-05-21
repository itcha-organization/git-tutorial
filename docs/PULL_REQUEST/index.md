# Pull request

## ¿Qué es un pull request?

En pocas palabras, un pull request es una función que notifica a otros desarrolladores los cambios en el repositorio local de un desarrollador.<br>
El pull request ofrece las siguientes funciones.

- Notificar los cambios a los revisores y otras partes interesadas, como funciones adicionales o modificaciones.
- Indicar claramente dónde se ha modificado el código.
- Proporcionar un foro de comunicación sobre el código.

El uso de pull requests puede ayudar a arraigar una cultura de revisión del código en la organización.<br>
Las revisiones del código permiten reducir los errores.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c534146b-be5f-408e-b3a1-af908de38191)

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

①[ desarrollador ] Realice un clone o pull para obtener el código en el repositorio remoto con el que está trabajando.<br> 
②[ desarrollador ] Crear un branch de trabajo en el repositorio local.<br>
③[ desarrollador ] Modificar el código.<br>
④[ desarrollador ] Cuando el trabajo esté terminado, realice un push.<br>
⑤[ desarrollador ] Crear un pull request.<br>
⑥[ revisor ] Compruebe y revise los cambios de la pull request notificada.<br>
⑦[ revisor ] Determine los resultados de la revisión y proporcione información al desarrollador si es necesario.<br>
⑧[ revisor ] Si, tras la revisión, no hay problemas, fusiona.<br>
⑨[ revisor ] Si, como resultado de la revisión, la pull request en sí ya no es necesaria, por ejemplo, la respuesta en sí ya no es necesaria, la pull request se cierra.

Repita los pasos 3-7 anteriores tantas veces como sea necesario. Como resultado, se puede mejorar la calidad del código fusionado final.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e41d1cc1-44af-40e7-952d-b8dc543b6b87)

