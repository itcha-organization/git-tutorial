# Compartir repositorios

## Realizar push a un repositorio remoto.

Hasta ahora, hemos descrito el uso básico de un repositorio local.<br>
Esta sección describe ahora cómo compartir el historial de cambios del repositorio local utilizando un repositorio remoto.

### Push

Para compartir el historial de cambios de su propio repositorio local en un repositorio remoto, necesita subir el historial de cambios en el repositorio local.

Para ello, Git realiza una operación llamada `Push`.<br>
Cuando realiza un `Push`, su historial de cambios se sube al repositorio remoto, de forma que el historial de cambios en el repositorio remoto es el mismo que el historial de cambios en el repositorio local.

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/93ee162d-34c7-4a56-be7c-2ad54a0a098d)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/52c9455d-cc61-4aa5-99a5-d91a10e54c24)

## Clonar repositorios remotos.

Si dispone de un repositorio remoto que contiene el historial de cambios de otra persona, puede duplicarlo en su totalidad y trabajar en él usted mismo.

### Clone

Para duplicar un repositorio remoto, realice la operación `Clone`.

Cuando ejecuta clonar, puede descargar todo el contenido del repositorio remoto y crearlo como repositorio local en otra máquina.

Hay dos formas de crear un repositorio en Git, una usando el comando `git init` y la otra usando este comando `git clone`.

___
##### Consejo
El repositorio local clonado es también un duplicado del historial de cambios, por lo que puede consultar el historial y confirmar exactamente como lo hizo en el repositorio original.
___

## Realice un pull contra el repositorio remoto.

Cuando compartes un repositorio remoto y varias personas trabajan en él, todo el mundo empuja al repositorio remoto.
A continuación, debe incorporar los cambios introducidos por los demás en su repositorio local.

### Pull

Para actualizar el repositorio local desde un repositorio remoto, utilice la operación `Pull`.

Ejecutando `Pull` descargará el último historial de cambios del repositorio remoto e incorporará su contenido a su repositorio local. 

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/ef14dfa3-6d79-40fd-b0e8-aec3add6eada)

![image](https://github.com/itcha-organization/git-tutorial/assets/83223664/fa274df1-fec6-4445-aadb-d6ba2d965933)



## Diferencias entre Pull y Fetch

https://backlog.com/ja/git-tutorial/stepup/14/

### Pull

Puede ejecutar `pull` para obtener el historial del repositorio remoto. El siguiente diagrama ilustra lo que ocurre con las confirmaciones en el repositorio en este momento.

まずは、更新されるローカルリポジトリのブランチに何の変更も行なっていなかった場合を見てみます。


この場合は、単にfast-forwardマージが行われます。図中のmasterはローカルリポジトリのmasterブランチ、origin/masterはリモートリポジトリ origin のmasterブランチを表します。

もし、ローカルリポジトリのmasterブランチでも履歴を進めていた場合は、両方の変更を統合する必要があります。

そのため、pullを実行するとマージが行われます。この時、競合する変更がなければ自動的にマージコミットが作られます。しかし、競合があった場合は、それを解決してから自分でコミットする必要があります。
