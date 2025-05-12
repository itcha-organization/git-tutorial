# Práctica: Trabajo colaborativo con Git y GitHub en un proyecto Laravel
- Actividades por grupo (3 - 5 integrantes)
- Comparteir un proyecto Laravel en un repositorio GitHub.

## Objetivo
Fortalecer el uso de Git y GitHub para el trabajo colaborativo en equipo con un proyecto Laravel, incluyendo: creación del repositorio, clonación, trabajo en ramas, resolución de conflictos

## Parte 1: Creación del proyecto y configuración inicial (Responsable: Lider)
-	Crear un nuevo proyecto Laravel: `orders-app`:
  ```
  composer create-project laravel/laravel orders-app
  ```
-	Ingresar al proyecto:
-	Habilitar archivo de rutas `api.php`:
  ```
  php artisan install:api
  ```
-	Crear archivo .env.example si no existe:
- Inicializar repositorio Git:
- Crear el primer commit con la descripción “Configuración inicial”
- Crear repositorio privado en GitHub con el mismo nombre del Proyecto y enlazarlo:
- En la página del repositorio que ha creado, haga clic en `Invite colaborators` para **invitar a los miembros del equipo**.
- Vincular repositorio local con repositorio remote
- Subir cgitommit inicial

## Parte 2: Clonación y configuración de entorno local (Responsables: Colaboradores)
- Clonar el repositorio
- Entrar a la carpeta del Proyecto
- Instalar dependencias:
  ```
  composer install
  ```
- Copiar el archivo `.env` a partir del archive `.env.example`
  ```
  cp .env.example .env
  ```
- Configurar el `.env` (En desarrollos reales., hay que crear una base de datos e introducir la información de conexión en `.env`.)
- Ejecutar migraciones
  ```
  php artisan migrate
  ```

## Parte 3: Distribución de tareas (Responsables: Colaboradores)
- Divida las siguientes cuatro tareas entre los miembros, excluyendo al líder.(Los equipos de cuatro sólo tienen las tareas 1-3.)
1. Colaborador 1 – crear API para marcas (migración, modelo y controlador)
2. Colaborador 2 – crear API para categorías (migración, modelo y controlador)
3. Colaborador 3 – crear API de productos (migración, modelo y controlador)
4. Colaborador 4 – crear API de clientes (migración, modelo y controlador)

##  Parte 4: Creación de ramas (Responsables: Colaboradores)
- Cada colaborador debe crear una rama propia para trabajar:
  ```
  git checkout -b nombre-rama
  ```
  > Ejemplo: `git checkout -b api-marcas`

## Parte 5: Trabajar en sus propias tareas y crear ***commit*** (Responsables: Colaboradores)
- Crear API para migración, modelo y controlador **(Sólo se pueden crear archivos y omitir la codificación.)**
- Todos los colaboradores deben agregar las rutas en el archivo `api.php`, para acceder a los diferentes endpoint de cada API
- Crear un commit con la descripción de sus propias tareas

## Parte 6: Subir ramas y crear ***Pull Request*** (Responsables: Colaboradores)
- Subir rama al repositorio GitHub
  ```
  git push -u origin nombre-rama
  ```
    > Ejemplo: `git push -u origin api-marcas`
- Iniciar sesión en GitHub y acceder al repositorio del proyecto en navegador.
- Haga clic en `Compare & pull request` para fusionar su rama propia en `main`
- Asegúrese de que base(la rama de destino) es la rama `main` y compare(la rama de origen) es la rama que subió.
- Después, Haga clic en `Create pull request`

## Parte 7: Resolver conflictos (Responsables: Colaboradores)
Si no se puede realizar una fusión debido a un conflicto, se pueden seguir los siguientes pasos para resolver el conflicto.

**1. Ejecutar un pull hacia `main` de remoto.** <br>
   En primer lugar, en la rama en la que está trabajando, ejecuta `git pull` hacia `main` de remoto.<br>
   De este modo, los últimos commits en `main` de remoto se incorporan al su propia rama.
   ```
   git pull origin main
   ```

**2. Resolver los conflictos en el repositorio local.** <br>
   Tras ejecutar el comando pull, se produce un conflicto local. Compruébalo con el comandos `git status`.<br>
   Abra el archivos con conflict y resuelva los conflictos manualmente. (El procedimiento es el mismo que el aprendido en el tema de branch.)

**3. Vuelva a ejecutar commit y push después de modificar el código.** <br>
   Cree un commit y complete la resolución del conflicto.
   A continuación, suba a la misma rama en el remoto y refleje la adición de commit.

## Parte 8: Verificar que los colaboradores hagan las tareas asignadas y fusionar Pull Request (Responsables: Colaboradores)
Cada vez que un miembro crea un pull request, el líder debería verificarlo y fusionarlo.
