# Guía de operaciones

## リモートリポジトリをClone、初回のみの操作

Hay dos formas de crear un repositorio local en Git, una usando el comando `git init` y la otra usando este comando `git clone`.<br>
Para el desarrollo en equipo, en la mayoría de los casos se utiliza `git clone` para clonar el repositorio remoto y crear un repositorio local.

Ejecute el siguiente comando para crear un repositorio local que replique el repositorio remoto.
Además, en el caso de `git clone`, el repositorio remoto `origin` se registra automáticamente, así que compruébalo también.

```
$ git clone <repositorio> <directorio>
$ cd <directorio>
$ git remote -v
```

Se trata de un procedimiento que sólo es necesario realizar la primera vez que se crea un nuevo repositorio.

## Crear Issues

### Resumen de `Issues`

`Issues` es una función para describir y gestionar informes de errores, peticiones de funciones y tareas.<br>
Algunos ejemplos de ventajas concretas son

* **Seguimiento y gestión de problemas:** <br>
  GitHub Issues permite seguir y gestionar eficazmente problemas y tareas dentro de un proyecto. Puedes describir claramente los problemas y organizarlos con etiquetas y hitos.
* **Colaboración:** <br>
  Cuando trabajan varias personas en un proyecto, GitHub Issues facilita la colaboración. Se pueden hacer comentarios en los problemas, asignarlos a personas y relacionarlos con solicitudes de extracción de manera sencilla.
* **Búsqueda y filtrado:** <br>
  Los Issues cuentan con funciones de filtrado y búsqueda, lo que facilita el acceso rápido a la información necesaria y hace que el seguimiento de problemas sea más fácil incluso en proyectos grandes.

### Cómo utilizar Issues

Seleccione `Issues` en la pestaña correspondiente del proyecto en GitHub.Haga clic en `New issue`.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/2e53b562-cd03-476d-a439-ca8a7fa272a2)

Rellene el título y el contenido del `issue` y haga clic en `Submit new issue`.<br>
El siguiente texto es una plantilla de contenido. Cópielo, péguelo y utilícelo.

```
### Descripción de la tarea

* Para gestionar Carrera con estado, es necesario añadir estado al modelo de Carrera.
* Para gestionar Ciclo con codigo, es necesario añadir codigo al modelo de Ciclo.
```

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/392fa867-efb2-4ff4-b6ab-a3a7f61254b6)

## Editar código en el repositorio local.

Crea un nuevo branch de trabajo para el `issue` registrado y empieza a editar el código.<br>
Los branches se nombran según el formato.<br>
`feature/issue-<Número de branch>-<Título abreviado de la issue>`

Ejemplo:

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/c3831cc1-48e5-4d34-add0-a6fd386cdb12)

git branch 新規ブランチ名_#issue番号としてissue番号を付けておくと今後見やすくて便利
git checkout 新規ブランチ名で作業ブランチに移動することを忘れない
ブランチの移動まで一括で行いたい場合は、git checkout -b 新規ブランチ名_#issue番号として実行する。-bオプションは「ブランチの作成（branchのb）」のこと。

キリの良いところで適宜コミットする（git commit -m "コミットメッセージ #issue番号"）

コミットする時必ず対応するissue番号を半角スペースを空けて付け加えること！（こうすることで、そのIssueに関するコミットだということを紐付けることが出来る）

作業が完了したら適宜git pushする（全て終わってからじゃなくてもOK）

この時作業ブランチ宛にpushすることに注意！（git push origin 作業ブランチ名 または、 git push origin HEAD）

## pull requestを作成する

## ローカルのmainブランチをリモートブランチと同じ状態にする（git pull origin main）

git checkout mainでmainブランチに移動する
git pull（git pull origin main）する（チーム開発においては「git fetch + git merge」の方が無難かも）
git pullしたあとはローカルでmerge commitが作成されるので、ここで一度git pushしてリモートのmainブランチを更新しておいたほうがいいかも。（因みに、このmerge commitの作成を回避するためには、git pull --rebaseコマンドを使うといいとかなんとか）
