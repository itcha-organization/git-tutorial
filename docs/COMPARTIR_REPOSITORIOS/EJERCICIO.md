# Ejercicios de compartir repositorios

## Pregunta 1

Cree una carpeta `~/ejercicio3` y colócala bajo control Git.<br>
En el directorio `~/ejercicio3`, cree un archivo llamado `compartir_repositorios.txt` y haga commit.<br>
Luego compruebe el historia de commit.

## Pregunta 2

Ve a GitHub en su navegador y cree un repositorio privado, llamado `ejercicio3`.

## Pregunta 3

Registre el repositorio remoto `ejercicio3` creado en la pregunta 2 como remoto del repositorio local `ejercicio3` usando comandos en GitBash.<br>
A continuación, realice un push para reflejar los cambios en el repositorio remoto.<br>
Luego, compruebe que el historial de commits y el archivo se han añadido en GitHub.

## Pregunta 4

Clone el repositorio remoto `ejercicio3` y cree un repositorio local `ejercicio3-clone`.<br>
Luego vaya al directorio `ejercicio3-clone` y compruebe el historia de commit y el archivo en el repositorio local `ejercicio3-clone`.

## Pregunta 5

Añade el siguiente texto a `compartir_repositorios.txt` y ejecuta commit en `ejercicio3-clone`. Luego compruebe el historia de commit.

```
Resume de compartir repositorios
Push: sube su historial de cambios al repositorio remoto
Clone: puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local
Pull: descarga el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local
Remote add: puede nombrar y registrar la dirección del repositorio remoto para no tener que introducir una larga dirección de repositorio remoto cada vez
```

## Pregunta 6

En `ejercicio3-clone`, ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio3`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.

## Pregunta 7

Primero, vaya al directorio `~/ejercicio3` y compruebe el historial de commits y el contenido del archivo.<br>
A continuación, obtenga los últimos cambios del repositorio remoto en el repositorio local `ejercicio3` usando pull.<br>
Luego, compruebe el historial de commits y el contenido del archivo de nuevo.

## Pregunta 8

En el repositorio local `ejercicio3`, cree un branch `añadir_descripción_de_origin` y ve a el branch.<br>
Añade el siguiente descripción de `origin` al final del `compartir_repositorios.txt` y ejecute commit.

```
origin: Si el nombre del repositorio remoto se omite en tiempo de ejecución, el push o pull utilizará el repositorio remoto llamado origin
```

## Pregunta 9

En el repositorio local `ejercicio3`, ejecute un push para reflejar el cambio en el repositorio remoto `ejercicio3`.<br>
Luego, compruebe que el historial de commits y el archivo en GitHub.
