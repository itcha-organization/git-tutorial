# Ejercicio 2: Resolver conflicto y actualizar `Pull Request`

# PARTE 1

1. Clonar un repositorio remoto de GitHub y crear un repositorio local

- Abra el siguiente repositorio remoto de GitHub en otra pestaña.
  https://github.com/kkk-commit/conflict-practice

- En GitBash, utilice el comando `clone` para clonar un repositorio. `<repositorio>` es la URL del repositorio remoto y `<directorio>` es el nombre del directorio a clonar.

> ```
> $ git clone <repositorio> <directorio>
> ```

2. Crear una nueva rama a partir de main.

3. Editar el archivo team.txt agregando su propia información.

4. Crear un Pull Request.

5. Resolver cualquier conflicto que surja antes de hacer merge.

<details>

<summary>Pasos para resolver conflicto y actualizar `Pull Request`
</summary>

## Pasos para resolver conflicto y actualizar `Pull Request`

Si surgen conflictos, edite y fusione el código manualmente.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/86873e5a-325f-4156-a16c-b702f965379e)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/22abde12-a64c-48b0-b679-988d12fe6706)

### 1. Ejecutar un pull hacia el branch master.

En primer lugar, en el branch en el que está trabajando, ejecuta un pull hacia el branch destino de la `pull request`.<br>
De este modo, los últimos cambios en el branch de destino de la `pull request` se incorporan al branch de trabajo.

```
$ git checkout ★nombre de branch de trabajo★
$ git pull origin master
```

### 2. Resolver los conflictos en el repositorio local.

Tras ejecutar el comando pull, se produce un conflicto local. Compruébalo con el comandos `git status`.

### 3. Vuelva a ejecutar commit y push después de modificar el código.

Ejecute los siguientes comandos para commit y push.

</details>

# PARTE 2

1. Utilice `git pull` para modernizar su branch `main` local.

2. Crear una nueva rama a partir de main.

3. Editar los archivos `birthdays.txt` y `hobbies.txt` agregando su propia información.

4. Crear un Pull Request.

5. Resolver cualquier conflicto que surja antes de hacer merge.