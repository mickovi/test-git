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

## Añadir Repositorios Remotos

```console
$ git remote
$ git remote add [nombre-remoto] [url]
$ git remote -v

```

## Traer y Combinar Remotos

```console
$ git fetch [nombre-remoto]
$ git pull
```
## Enviar a tus remotos

```console
$ git push [nombre-remoto] [nombre-rama]
```


$ git reflog

```console
```