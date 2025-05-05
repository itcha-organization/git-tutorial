# Tutorial: Experimentar el GitHub Flow

En este tutorial, experimentarás el GitHub Flow, desempeñando el papel de líder y miembro solo.

- En primer lugar, como líder, cree un repositorio remoto y subir el commit initial.
- A continuación, como miembro, añade un archivo resumen de los comandos que hemos aprendido y fusiona los cambios en GitHub utilizando **Pull Request**.

## Líder: Cree un repositorio remoto en GitHub

Primero, acceda a github e inicie sesión.
![https://github.com/](https://github.com/)

Haga clic en `el icono +` > `New repository`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ac3cd9c5-8fd9-4f6b-8732-e292b90aa612)

Introduzca el "Repository" y la "Description", seleccione acceso `Private` y pulse el botón `Create repository`. <br>
Aquí, introduje `tutorial-repo` en el nombre y `para tutorial de repositorio remoto` en la descripción.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/a794490a-00b3-4f51-8c85-ecaeb712a201)

Se añade un nuevo repositorio, como se muestra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/667d04d7-7d00-444d-8dad-7396f8637abe)

La situación actual se ilustra en el siguiente diagrama.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/afc592c6-b1c0-4bf0-87c4-9c530ca8e884)

## Líder: Realiza un push contra el repositorio remoto.

### Repaso: Cree un repositorio local y realize el primer commit.

Siga los siguientes comandos, cree un repositorio local llamado `tutorial-repo` y un archivo llamado `README.md` y haga el commit initial. <br>
```
mkdir ~/tutorial-repo
```
```
cd ~/tutorial-repo
```
```
git init
```
```
echo "# tutorial-repo" >> README.md
```
```
git status
```
```
git add README.md
```
```
git status
```
```
git commit -m "commit inicial"
```
```
git log
```
> ![image](https://github.com/user-attachments/assets/4f712bd1-2a3f-49b0-a28c-6fffdffa9c6a)

### Registrar un repositorio remoto y realizar un push.

Ejecute push para enviar el historial del repositorio local al repositorio remoto.

Se puede nombrar y registrar la dirección del repositorio remoto.<br>
Grábala para no tener que introducir una larga dirección de repositorio remoto cada vez que realice un push.<br>
En primer lugar, registre un repositorio remoto con el nombre `origin` y, a continuación, realice un push.

Para añadir un repositorio remoto, utilice el comando `remoto`. `<nombre>` es el nombre del registro y `<url>` es la URL del repositorio remoto
> ```
> $ git remote add <nombre> <url>
> ```

En navegador, copie el URL del repositorio remoto creado.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2f232723-6a7a-4366-8e50-fbba09422165)

Ejecute el siguiente comando para registrar la URL del repositorio remoto creado en la página anterior con el nombre `origin`. Sustituya la `★su propia url★` por la URL que acaba de copiar y ejecute.

```
git remote add origin ★su propia url★
```
> ![image](https://github.com/user-attachments/assets/b9e82cb3-321e-4a9b-a630-0ff651ce24be)

El siguiente comando se puede utilizar para comprobar los repositorios remotos registrados.
```
git remote -v
```
> ![image](https://github.com/user-attachments/assets/a4c13e85-0164-4943-a507-93106bf13f50)

> [!NOTE]
> Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado `origin`.
> Por este motivo, es habitual denominar a los repositorios remotos `origin`.

Para realizar un push a un repositorio remoto, utilice el comando `push`.<br>
`<repositorio>` especifica el repositorio remoto al que hacer push y `<refspec>` el branch a el que hacer push.
> ```
> $ git push <repositorio> <refspec>...
> ```

Ejecute el siguiente comando para realizar un push contra el repositorio remoto `origin`.<br>
Si utilizar `-u` como opción, puede omitir especificar el nombre del branch la próxima vez.<br>
Sin embargo, al hacer push contra el primer repositorio remoto vacío, no puede omitir el nombre del repositorio remoto o el nombre del branch.
```
git push -u origin main
```
> ![image](https://github.com/user-attachments/assets/ca981fbc-5ee7-45ce-b1ad-d4a3e0887bd3)

Abra la página de Github.<br>
Compruebe que el repositorio se ha actualizado y que se ha añadido archivo.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/9fd6ec3a-3ebd-4aae-a77b-b7a0477f2f63)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/0b5a1b6a-816d-4009-b7c1-d2e0dea1e566)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/df7e7c02-a9a6-46be-ae55-98755e2b984c)

![image](https://github.com/user-attachments/assets/bfa5d4d4-8f87-430f-bb46-e333b81b6b7a)

## Miembro: Clonar repositorios remotos.

A continuación, clone el repositorio remoto como si fueras otro usuario y crea un repositorio local `tutorial-repo-miembro`.

Utilice el comando `clone` para clonar un repositorio. `<repositorio>` es la URL del repositorio remoto y `<directorio>` es el nombre del directorio a clonar.
> ```
> $ git clone <repositorio> <directorio>
> ```

El siguiente comando crea el directorio `~/tutorial-repo-miembro` y clona allí el repositorio remoto especificado por la URL. Sustituya la `★su propia url★` por la URL suya y ejecute.
```
git clone ★su propia url★ ~/tutorial-repo-miembro
```
> ![image](https://github.com/user-attachments/assets/5adee167-1141-423c-8464-3917f4c3fe3b)

En el directorio creado `tutorial-repo-miembro`, abra VS Code y compruebe el contenido.
```
cd ~/tutorial-repo-miembro
```
```
code .
```

## Miembro: Realice un push desde el repositorio clonado.
Como miembro, añade un archivo resumen de los comandos que hemos aprendido.

Cree un branch de trabajo `resumen-comandos` con el siguiente comando y paes al branch.
```
git checkout -b resumen-comandos
```
> ![image](https://github.com/user-attachments/assets/b7ed980c-f582-4200-b130-8821492fd8c8)

Cree un achivo de texto llamado `comandos.txt` en el directorio `tutorial-repo-miembro`.
<br>
Abra el archivo y pegue el siguiente texto y guárdelo.
```
Tutorial de compartir repositorios
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
```
> ![image](https://github.com/user-attachments/assets/1690c828-2a18-44c4-bca1-aa9efd964140)

Con los siguientes comandos, creeun commit para guardar el cambio.
```
git add comandos.txt
```
```
git status
```
```
git commit -m "He agregao resumen de push, clone y pull"
```
```
git log
```
> ![image](https://github.com/user-attachments/assets/06a678c9-098a-4eaa-ac69-ffcabdfb4f9c)

A continuación, sube el branch `resumen-comandos` al repositorio remoto con el comando `push`.
```
git push -u origin resumen-comandos
```
> ![image](https://github.com/user-attachments/assets/074f9cac-69bc-4d60-9813-33d8632f2869)

Abre la página del repositorio `tutorial-repo` en Github.<br>
Compruebe que se ha subido el branch `resumen-comandos`.
> ![image](https://github.com/user-attachments/assets/faf1856b-fd45-4cf7-be0e-ea2e3e6b6b12)

## Miembro: Fusiona un branch de trabajo en `main` en GitHub utilizando **Pull Request**.
Cree una Pull Request para fusionar `resumen-comandos` en `main` según las siguientes imagenes.
> ![image](https://github.com/user-attachments/assets/953af052-7f64-48f8-95a7-e14b2c070aac)
> ![image](https://github.com/user-attachments/assets/2e731ea5-6b36-4190-a90a-19a8a69bafc6)

A continuación, fusione los Pull Request que haya creado.
> ![image](https://github.com/user-attachments/assets/5db151f2-7ba3-4fde-b3eb-0e6ace4a7a39)
> ![image](https://github.com/user-attachments/assets/f4b5974a-c401-4a9e-a2f8-4b0ddbb5f652)


Abra la pestaña `Code` y compruebe que se ha importado el archivo `comandos.txt`.
> ![image](https://github.com/user-attachments/assets/ad785196-67d7-4a3e-9cd6-474ac299aa7a)

Comprueba que el commit realizado en `resumen-commandos` ha sido importado a `main`.
<br>
Además, se crea un commit cuando se fusiona una Pull Request, por lo que hay tres commits en total.
> ![image](https://github.com/user-attachments/assets/7547a102-dfc7-4b03-9259-736bdd8807fd)

## Líder: Ejecute un pull para obtener los cambios en el repositorio remoto.

Sólo existe el commit initial en el repositorio local del líder `tutorial-repo`.　Obtenga los commits que subió al repositorio remoto como miembro.

Como con `push`, `<repositorio>` especifica el repositorio remoto y `<refspec>` el branch.
<br>
Si omite el nombre del repositorio, el pull se realiza contra el repositorio registrado con el nombre `origin`.
> ```
> $ git pull <repositorio> <refspec>...
> ```

En primer lugar, ejecute el siguiente comando para ir al repositorio `tutorial-repo`.<br>
Compruebe el historial de commits y el contenido de los archivos en `tutorial-repo`.
```
cd ~/tutorial-repo
```
```
git log
```

A continuación, realice un pull.
```
git pull origin main
```
> ![image](https://github.com/user-attachments/assets/1cad84b3-dd79-4b73-a5ed-aa0294adaf04)

Compruebe el historial de commits y el contenido de los archivos otra vez.<br>
Se ha añadido el commit en el historial. Además, se ha añadido el contenido del archivo.
```
git log
```
> ![image](https://github.com/user-attachments/assets/4ac6846f-cd69-40c1-b2a0-47f407208fb0)
