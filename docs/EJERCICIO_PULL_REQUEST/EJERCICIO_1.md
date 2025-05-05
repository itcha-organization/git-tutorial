# Ejercicio 1: Fusionar branch en repositorios remotos mediante `Pull Request`

## Clonar un repositorio remoto de GitHub y crear un repositorio local

Abra el siguiente repositorio remoto de GitHub en otra pestaña.
<br>
https://github.com/kkk-commit/proyecto-presentacion-perfil

Utilice el comando `clone` para clonar un repositorio. `<repositorio>` es la URL del repositorio remoto y `<directorio>` es el nombre del directorio a clonar.

> ```
> $ git clone <repositorio> <directorio>
> ```

En GitBash, el siguiente comando clona el repositorio remoto `proyecto-presentacion-perfil` y crea un repositorio local.
```
git clone git@github.com:kkk-commit/proyecto-presentacion-perfil.git ~/proyecto-presentacion-perfil
```
> ![image](https://github.com/user-attachments/assets/6aaa708a-0c95-4900-9efc-db8f4a270566)

Ejecute los siguientes comando para ir al repositorio local clonado y compruebe el historial de _commit_ y el archivo `README.md`.
```
cd ~/proyecto-presentacion-perfil
```
```
git log
```
```
cat README.md
```
> ![image](https://github.com/user-attachments/assets/bb81042a-894d-45a7-8214-147f1d70290e)

## Crear un archivo de perfil en el repositorio local y ejecutar commit.

Para empezar a trabajar, cree un branch del tema con el nombre `perfil-"su nombre"` y muévase a ese branch.

> ![image](https://github.com/user-attachments/assets/1649cd37-ab9b-4c4a-a30e-c8597144e7b8)

> [!NOTE]
>  Normalmente, el nombre de un branch es un resumen de la tarea separado por guiones,
> <br>por ejemplo `funcion-login`,`ui-modo-oscuro`.

> [!CAUTION]
>  Se desaconseja el uso de la `ñ` o de `caracteres acentuados(á, é, í, ó, ú)` en los nombres de branch.

Cree un archivo llamado `Perfil_"su nombre".md`, escribe su cumpleaños y guarde el archivo.

> ![image](https://github.com/user-attachments/assets/927179e2-48e6-4db2-ba16-a072da9cce58)
> ![image](https://github.com/user-attachments/assets/814c58db-29be-4745-9737-198d28193f17)

> [!NOTE]
>  `.md` es un archivo en formato Markdown, un tipo de lenguaje que puede convertir texto plano escrito en notación simple en HTML y otros formatos.

Cree un commit y guarda los cambios en el repositorio local.

> ![image](https://github.com/user-attachments/assets/3da79e72-217b-45dd-976a-dc6cd5b05dd9)

## Subir el cambio al repositorio remoto con `push`.

Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
`<repositorio>` especifica el repositorio remoto al que hacer push y `<refspec>` el branch a el que hacer push.

```
$ git push <repositorio> <refspec>...
```

Sustituya el segundo argumento del siguiente comando por el nombre de su propio branch y ejecute el comando.
```
git push origin "el nombre de su branch"
```
> ![image](https://github.com/user-attachments/assets/52f0f5bf-9f62-462b-89a5-52d9962a77b7)

> [!NOTE]
> **origin**:
> Si ejecutas `git clone`, el repositorio remoto tendrá `origin` como nombre por defecto.

## Comprobar branch subido en GitHub.
Abra el repositorio remoto de GitHub en su navegador y compruebe que se ha añadido el branch que ha subido.
<br>Repositorio remoto de GitHub: https://github.com/kkk-commit/proyecto-presentacion-perfil

> ![image](https://github.com/user-attachments/assets/0a299244-c40b-42d7-8459-d875defc0667)

## Crear ***Pull Request***
Vamos a crear un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.

Haga clic en `Compare & pull request`
> ![image](https://github.com/user-attachments/assets/0ad9089b-e7ef-4986-ac50-dfeedc71019f)

Asegúrese de que _base_(el branch de destino) es el branch `main` y _compare_(el branch de origen) es el branch que subió.
<br>
Después, Haga clic en `Create pull request`
> ![image](https://github.com/user-attachments/assets/40980a6f-d43f-4dd9-878a-f63626b5aa1e)

La siguiente imagen muestra el `Pull Request` creada.
> ![image](https://github.com/user-attachments/assets/7b8624d8-7c86-4d27-a3b1-3dbffd856648)

## Fusionar ***Pull Request***
Como esto es un tutorial, nos saltaremos la revisión del código y fusionaremos la `Pull Request`.

Haga clic en `Merge pull request`.
Después, Haga clic en `Confirm merge`.
> ![image](https://github.com/user-attachments/assets/ddcc7013-f1c5-4de2-b1e3-971148e2e673)
> ![image](https://github.com/user-attachments/assets/b715c79b-fd36-47d6-bd6a-2d5fb0ccd7a7)

> [!CAUTION]
>  Lo ideal es pedir al jefe de equipo o a otro miembro del equipo que revise el código para asegurarse de que los cambios son aceptables.

## Comprobar que los cambios se han incorporado al `main`
Compruebe que se han añadido archivos.
> ![image](https://github.com/user-attachments/assets/df1e9a32-a598-4c1f-93ec-ab5725076953)

Compruebe que se ha actualizado el historial de commit.
> ![image](https://github.com/user-attachments/assets/7f063b7c-1274-43b2-9c72-b8db493fa1ba)
> ![image](https://github.com/user-attachments/assets/0eab55e7-00ab-48db-a43b-3c4a5b3c946e)


## Actualizar el repositorio local con `pull`
Utilice `pull` para reflejar los commits realizados por otros miembros en su repositorio local.

Como `push`, `<repositorio>` especifica el repositorio remoto y `<refspec>` el branch.
```
$ git pull <repositorio> <refspec>...
```

Ejecute el siguiente comando para reflejar el último estado del branch `main` del repositorio remoto en el repositorio local.
```
git checkout main
```
```
git pull origin main
```
> ![image](https://github.com/user-attachments/assets/a8df4b3b-3711-439f-b41a-37b348e47dab)

Ejecute el siguiente comando para comprobar que se han añadido el historial de commit y los archivos.
```
git log
```
```
ls -l
```
> ![image](https://github.com/user-attachments/assets/d83c639a-543e-40c4-a995-62c2023bc688)

## Editar archivos creados por otros miembros
Añada un mensaje de felicitación al **perfil de alguien cuyo cumpleaños sea uno después del suyo**.
- Para empezar, cree un branch del tema con el nombre `celebracion-"nombre de su compañero"` y muévase a ese branch
  ![image](https://github.com/user-attachments/assets/06e5d65c-c75a-4515-b815-c10f2bce0670)
- Añada un mensaje de felicitación al perfil de la persona cuyo cumpleaños es uno después del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
  ![image](https://github.com/user-attachments/assets/dd8f87b8-ba5d-44ad-a5c4-9cd0b2278bfc)
- Suba el cambio al repositorio remoto con `push`.
  ![image](https://github.com/user-attachments/assets/e9e9f46b-68c4-44a4-9204-cc2831db3935)
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.
- Fusione el `Pull Request` creado.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.

## Repaso: Editar archivos creados por otros miembros
Añada **lo que le gustaría recibir como regalo** al perfil de **alguien cuyo cumpleaños es uno antes que el suyo**.
- Para empezar, cree un branch del tema con el nombre `peticion-regalo-"su compañro"` y muévase a ese branch
- Añada lo que le gustaría recibir como regalo al perfil de la persona cuyo cumpleaños es uno **antes** del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
- Suba el cambio al repositorio remoto con `push`.
- Cree un `Pull Request` para integrar los cambios en el branch del tema en el branch `main` en el repositorio remoto.

En el archivo que acabas de editar, haz una nueva línea y añade **lo que quieras como segundo regalo**.
- Añada **lo que quieras como segundo regalo** al perfil de la persona cuyo cumpleaños es uno **antes** del suyo y guarde el archivo.
- Cree un commit y guarde el cambio.
- Suba el cambio al repositorio remoto con `push`.
- Abra la `Pull Request` que acaba de crear y compruebe que se ha añadido el commit.
- Fusione el `Pull Request` creado.
- Refleje los cambios de otros miembros en el repositorio local con `pull`.
