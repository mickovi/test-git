## **Agregar al Stage y confirmar**
*git add* es un comando que cumple varios propósitos -lo usas para empezar a rastrear archivos nuevos, preparar archivos, y hacer otras cosas como marcar archivos en conflicto por combinación como resueltos.

```console
$ git add *
$ git add README.md
```

```console
$ git commit -m "version 1.0"
$ git commit -am "version 1.0"
```

## **Estados de los archivos**

```console
$ git status
$ git status -s
$ git status --short
```


## **Modificaciones**

### 1. Mostrar las modificaciones en un commit:
*git diff* uestra los cambios que no están en el stage. 
*git diff --staged* muestra los cambios que están en el stage.

```console
$ git diff
$ git diff --staged
```

### 2. Corregir el mensaje de un commit:
git commit -am "Versión 1.2"
git commit --amend -m "Versión 1.23"

### 3. Modificar cambios de diferentes commits con reset:

```console
$ git reset --soft [HEAD^ | hash del commit]
$ git reset --mixed HEAD^2
$ git reset --hard HEAD^5
```

### 4. Modificar o eliminar archivos en git:

```console
$ git mv inde.html index.html
$ git rm index.html
```

*rm* solo lo elimina del directorio, pero sigue presente en el stage. Se puede recuperar con git checkout -- . o git reset --hard. Se puede hacer un commit aunque con un git reset --soft [hash del commit] se puede volver a recuperar (verificar).

## Ver el historial de commits (confirmaciones):

```console
$ git log
$ git log -p -2
$ git log --stat
$ git log --pretty=online
$ git log --pretty=format:"%h - %an, %ar : %s"
```

## Confirmar cambios

```console
$ git commit [archivo|carpeta] -m "mensaje"
$ git commit -am "mensaje"
```

## Deshacer cosas

```console
$ git commit --amend
$ git checkout -- [archivo]
```

## Añadir repositorios remotos

```console
$ git remote
$ git remote add [nombre-remoto] [url]
$ git remote -v

```

## Traer y combinar remotos

```console
$ git fetch [nombre-remoto]
$ git pull
```
## Enviar a tus remotos

```console
$ git push [nombre-remoto] [nombre-rama]
```

## Eliminar y renombrar remotos

```console
$ git remote rename [nombre-antiguo] [nombre-nuevo]
$ git remote rm [nombre-remoto]
```

## Etiquetado
```console
$ git tag
```

## Crear etiquetas
Existen dos tipos: 
1. Las etiquetas *ligeras* es muy parecido a una rama que no cambia ( simplemente es un puntero a un commit específico).
2. Las etiquetas *anotadas* se guardan en la base de datos de Git como objetos enteros.

### Etiquetas anotadas

```console
$ git tag -a v1.4 -m 'new version 1.4'
git show
```

### Etiquetas ligeras

```console
$ git tag v1.4-lw
git show
```

### Etiquetado tardío

```console
$ git tag -a [version] [checksum-del-commit]
git show
```
## Compartir etiquetas

### Etiquetado tardío

```console
$ git push [remoto] [version]
$ git push [remoto] --tags
```
## Sacar una etiqueta

En Git, no puedes sacar (check out) una etiqueta, pues no es algo que puedas mover. Si quieres colocar en tu directorio de trabajo una versión de tu repositorio que coincida con alguna etiqueta, debes crear una rama nueva en esa etiqueta:

```console
$ git checkout -b version v2.0.0
```
-> Switched to a new branch 'version2'
Obviamente, si haces esto y luego confirmas tus cambios, tu rama version2 será ligeramente distinta a tu etiqueta v2.0.0 puesto que incluirá tus nuevos cambios; así que
ten cuidado.

## Alias de Git
```console
$ git config --global alias.[mi_alias] [comando-git]
```
Ejemplos:

```console
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
```
Puedes crear tus propios comandos con alias. Por ejemplo, para ver el último commit:

```console
$ git config --global alias.last 'log -1 HEAD'
```

También puedes ejecutar un comando externo en
lugar de un subcomando de Git:

```console
$ git config --global alias.visual "!gitk"
```

$ git reflog