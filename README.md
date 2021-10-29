# **BlogPlatzi** :fire:
**Blog de prueba curso plazi github**

# **Apuntes**

## **Iniciar un proyecto local git**

```javascript
git init

```

## **Agregar archivos al repositorio - git add**

**Agregar todos los archivos pendientes a memoria**
```javascript
git add .
```

**Agregar archivo definido a memoria**
```javascript
git add Nombre_archivo
```

**Agregar multiples archivos definidos a memoria**
```javascript
git add Nombre_archivo1 Nombre_archivo2
```

## **Guardar cambios de archivos al repositorio local - git commit**

**Guardar cambios y enviar al repositorio local**
```javascript
git commit -m "mensaje"
```

**Agregar todos los archivos y enviar cambios al repositorio local**
```javascript
git commit -a -m "mensaje"
```

**Agregar todos los archivos y guardar al repositorio(solor funciona con archivos enviados anteriormente)**
```javascript
git commit -am "mensaje"
```

## **Verficiar estado de archivos - git status**
> Verificar si han ocurrido cambios en lo archivos del  repositorio
```javascript
git status
```

## **Eliminar archivos agregados al repositorio - git rm**

**Eliminar archivos agregados al repositorio de forma parcial**
```javascript
git rm --cached
```

**Eliminar archivos agragados al repositorio de forma forzada**
```javascript
git rm --forced
```

## **Configurar git**

**Ver configuraciones git**
> ver listado de configuraciones por defecto de git
```javascript
git config --list
git config -l
```

> ver listado de configuraciones por defecto de git con su ruta
```javascript
git config --list --show-origin
```

## **Configurar usuario git**

**Configurar el nombre en git**
```javascript
git config --global user.name "nombre"
```

**Configurar el correo en git**
```javascript
git config --global user.email "correo"
```

## **Ver los commits del repositorio - git log**

**Ver todos los commits hechos en el repositorio**
```javascript
git log
```

**Ver todos los commits del archivo definido**
```javascript
git log Nombre_archivo
```

**Ver todos los commits hechos en el repositorio de forma detallada**
```javascript
git log --stat
```

**Ver todos los commits hechos en todo el repositorio**
```javascript
git log --all
```

**Ver todos los commits en todo el repositorio viendo el flujo de ramas**
```javascript
git log --all --graph
```

**Ver todos los commits viendo el flujo de ramas de forma complimida y resumida**
```javascript
git log --all --graph --decorate --oneline
```

## **Ver los cambios en el codigo del repositorio**

**Ver los cambios del codigo del respotorio**
```javascript
git show
```

**Ver los camnios en el codigo del repositorio de un archivo determinado**
```javascript
git show Nombre_archivo
```

**Ver los commits asociados a las tags**
```javascript
git show-ref --tags
```

## **Comparar la version del codigo - git diff**
> Ver la comparacion de codigo del ultimo cambio guardado con **git add**
```javascript
git diff
```

> ver la comparacion del codigo de diferentes versiones
```javascript
git diff CommitA CommitB
```

## **Volver en el tiempo los commits**

> Volver en el tiempo al commit teniendo en cuenta su Tag identificador(forma forsoza)
```javascript
git reset CommitA --hard
```

> Volver en el tiempo al commit teniendo en cuenta su Tag identificador pero poder recuperar en memoria
```javascript
git reset CommitA --soft
```

> Volver en el tiempo a la version mas actual de los commits
```javascript
git reset HEAD
```

## **Ir a una version**
> Ir a la version definida teniendo en cuenta el Tag identificador
```javascript
git checkout CommitA
```

> Ir a la version definida en el archivo especifico definido
```javascript
git checkout CommitA Nombre_archivo
```

> Volver los archivos a como estaban inicialmente
```javascript
git checkout main
```
### **Cambio de ramas**

> Moverse de la rama actual a la rama definida
```javascript
git checkout Nombre_rama 
```

## **Fusion de ramas**

> Fusionar la rama actual con la rama definida
```javascript
git merge Nombre_rama
```

> Fusionar la rama actual con la rama definida y poniendole un mensaje 
```javascript
git merge Nombre_rama -m "mensaje"
```

## **Remotos en git**

**Agregar al repositorio local un remoto que comunmente se llama 'origin' que apunta a una Url del repositorio remoto en Github**
```javascript
git remote add origin Url_repositorio
```

**Ver los remotos existentes en el respotorio local**
```javascript
git remote
```

**Ver el remoto de manera verbal(Nombre_remoto Url_repositorio)**
```javascript
git remote -v
```

**Modificar la url del remoto**
```javascript
git remote set-url Nombre_remoto Url_remoto
```

## **Actualizar los cambios del repositorio**

**Actualizar los cambios del repositorio local con los del repositorio remoto**
```javascript
git pull Nombre_remoto Nombre_rama
```
> Por ejemplo tengo un remoto que lo llame "origin" y una rama que la llame "main"
> El commando de git seria el siguiente
> - git pull origin main

**Actualizar los cambios del repositorio local con los del repositorio remoto(Forma forzada)**
```javascript
git pull Nombre_remoto Nombre_rama --allow-unrelated-histories
```

## **Alias en git**
**Crear un alias de un comando git**
```javascript
alias Nombre_alias="comando git"
```
> Un alias es una forma reducida o diferente de un mismo commando git
> por ejemplo si tengo el siguiente comando de git
```javascript
git log --all --graph --decorate --oneline
```
> si le damos un alias llamado "arbolito" para usarlo hacemos lo siguiente
```javascript
alias arbolito="git log --all --graph --decorate --oneline"
```

## **Tags en git y github**

**Ver las tags existentes**
```javascript
git tag
```

**Agregar una tag con un nombre definido y un mensaje**
```javascript
git tag -a Tag_name -m "mensaje"
```

**Eliminar una tag con nombre definido(No se eliminar del repositorio remoto)**
```javascript
git tag -d Tag_name
```

**Eliminar tag del repositorio remotor definiendo la tag**
```javascript
git push origin :refs/tags/Tag_name
```

## **Clonar repositorio**
> Clonar un respositorio remoto a uno local
```javascript
git clone Url_remoto
```

## Pull request

> Para subir cambios al fusionar a la rama principal por ejemplo "main" usando 'PULL REQUEST'.
> Esto es una caracteristica de Github que permite que al fusionar una rama a la rama principal se tenga que llegar a confirmar la fusion o 'merge'
> por el dueño del repositorio y/o contricullentes(Con o sin acceso)

> De esta forma la persona que quiere fusionar su rama con la principal tenga que esperar 
> una CONFIRMACION del dueño del repositorio o PETICION_DE_CAMBIOS para confirmar el merge

