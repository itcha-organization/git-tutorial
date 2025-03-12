# Configuración inicial

Si ya ha completado la configuración, puede practicar los comandos en siguiente pagina.<br>
https://learngitbranching.js.org/?locale=es_AR
___

## Instalación y configuración inicial de Git en Windows

Siga los pasos del siguiente artículo para instalarlo.<br>
https://www.neoguias.com/instalar-git-windows/

Una vez instalado, inicia `Menú Inicio` > `Todos los programas` > `Git` > `Git Bash`.

Aquí usaremos el comando `config` para configurar los ajustes. <br>
Ejecute el siguiente comando para establecer el nombre de usuario y la dirección de correo electrónico, que se registran en commit.
```
git config --global user.name "<Nombre de usuario>"
```
```
git config --global user.email "<Dirección de correo electrónico de la escuela>"
```
> Ejemplo:<br>
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/139957ee-cf22-44c2-885c-1cc08785f529)

> [!NOTE]
>  La configuración de git se registra en un archivo `.gitconfig` que se crea en el directorio home del usuario. Puede editar el archivo directamente.

## Creación de una cuenta en GitHub con la correo electrónico de la escuela

Cree una cuenta GitHub con la correo electrónico de la escuela de acuerdo con [la documentación oficial: Creación de una cuenta en GitHub](https://docs.github.com/es/get-started/start-your-journey/creating-an-account-on-github#signing-up-for-a-new-personal-account).

> [!CAUTION]
>  Si ya tiene una cuenta personal, siga [la documentación oficial: Agregar una dirección de correo electrónico a tu cuenta de GitHub](https://docs.github.com/es/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/adding-an-email-address-to-your-github-account) para añadir el correo electrónico de la escuela a su cuenta.


## Cómo generar una clave SSH y agregarla a GitHub
- Registrar una clave SSH tiene ventajas como la simplificación de la autenticación y la mejora de la seguridad.
- Una vez configurada, podrás acceder de forma segura a GitHub sin necesidad de contraseña cada vez que ejecutes un comando.

### Cómo generar una nueva clave SSH

Ejecute el siguiente comando, reemplazando el parámetro de segundo opcion por tu dirección de correo.<br>
Tras ejecutar el comando, aparecen varias preguntas. **No escriba nada y pulse Intro.**
```
ssh-keygen -t ed25519 -C "Dirección de correo electrónico de la escuela"
```
> Ejemplo:<br>
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/e343c7e6-1b6d-4410-b1f5-906d8617fb50)

> [!NOTE]
>  Al ejecutar `ssh-keygen` se generará un archivo de clave pública `id_ed25519.pub` en la carpeta `~/.ssh/`.<br>
>  Copiar el contenido del archivo `id_ed25519.pub` y registrarlo en GitHub para habilitar la autenticación SSH.

### Cómo agregar una clave SSH a tu cuenta de GitHub
En GitBash, ejecute el siguiente comando para copiar la clave pública que es el contenido del achivo `id_ed25519.pub`.<br>
Este comando copiará el contenido del achivo `id_ed25519.pub`, que podrá pegarse con control + v.
```
clip < ~/.ssh/id_ed25519.pub
```

Siguiente, acceda a su cuenta de GitHub mediante su navegador y acceda a la configuración de su cuenta haciendo clic en la foto de perfil de la parte superior derecha del menú y luego en ⚙`Settings`.
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/6c618047-5948-49c7-bfb2-482feba52c99)

Haz clic en la opción 🔑`SSH and GPC keys` que verás en la sección `Access` del menú de la izquierda.<br>
Haz clic en `New SSH Key`.
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/b381e960-bd38-4bbf-822c-4bb75093f2a1)

Para identificar el dispositivo asociado a la clave, introduzca cualquier texto, como la marca del dispositivo, en el campo `Título`.
Deje el campo `Key type` como está.

A continuación, pegue el contenido de `~/.ssh/id_ed25519.pub` copiado anteriormente en el campo `Key`.
Por último, haga clic en el botón `Add SSH key`.

Introduzca la contraseña de su cuenta cuando se le solicite.
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/499d1602-c212-4718-999d-a4a5da1bc521)

Ejecute el siguiente comando para comprobar la conexión
```
ssh -T git@github.com
```
> Ejemplo:<br>
> ![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/25d3b534-44d2-497b-8689-77f1397882b4)

#### Página de referencia.
- [Documentación de GitHub: Configuración de Git](https://docs.github.com/es/get-started/git-basics/set-up-git)
- [Documentación de GitHub: Conectar a GitHub con SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh)
- [Cómo generar una clave SSH y agregarla a GitHub](https://www.neoguias.com/generar-clave-ssh-agregar-github/)
