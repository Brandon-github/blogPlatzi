# **BlogPlatzi** :fire:
**Blog de prueba curso plazi github**

# **Apuntes**

## **Iniciar un proyecto local git - init**

```javascript
git init
```

## **Agregar archivos al repositorio - add**

### **Agregar todos los archivos pendientes a memoria**
```javascript
git add .
```

### **Agregar archivo definido a memoria**
```javascript
git add Nombre_archivo
```

### **Agregar multiples archivos definidos a memoria**
```javascript
git add Nombre_archivo1 Nombre_archivo2
```

## **Guardar cambios de archivos al repositorio local - commit**

### **Guardar cambios y enviar al repositorio local**
```javascript
git commit -m "mensaje"
```

### **Agregar todos los archivos y enviar cambios al repositorio local**
```javascript
git commit -a -m "mensaje"
```

### **Agregar todos los archivos y guardar al repositorio(solor funciona con archivos enviados anteriormente)**
```javascript
git commit -am "mensaje"
```

## **Verficiar estado de archivos - status**
> Verificar si han ocurrido cambios en lo archivos del  repositorio
```javascript
git status
```

## **Eliminar archivos agregados al repositorio - rm**

### **Eliminar archivos agregados al repositorio de forma parcial**
```javascript
git rm --cached
```

### **Eliminar archivos agragados al repositorio de forma forzada**
```javascript
git rm --forced
```

## **Configurar git - config**

### **Ver configuraciones git**
> ver listado de configuraciones por defecto de git
```javascript
git config --list
git config -l
```

> ver listado de configuraciones por defecto de git con su ruta
```javascript
git config --list --show-origin
```

## **Configurar usuario git - config --global user.value**

### **Configurar el nombre en git**
```javascript
git config --global user.name "nombre"
```

### **Configurar el correo en git**
```javascript
git config --global user.email "correo"
```

## **Ver los commits del repositorio - git log**

### **Ver todos los commits hechos en el repositorio**
```javascript
git log
```

### **Ver todos los commits del archivo definido**
```javascript
git log Nombre_archivo
```

### **Ver todos los commits hechos en el repositorio de forma detallada**
```javascript
git log --stat
```

### **Ver todos los commits hechos en todo el repositorio**
```javascript
git log --all
```

### **Ver todos los commits en todo el repositorio viendo el flujo de ramas**
```javascript
git log --all --graph
```

### **Ver todos los commits viendo el flujo de ramas de forma complimida y resumida**
```javascript
git log --all --graph --decorate --oneline
```

## **Ver los cambios en el codigo del repositorio - show**

### **Ver los cambios del codigo del respotorio**
```javascript
git show
```

### **Ver los camnios en el codigo del repositorio de un archivo determinado**
```javascript
git show Nombre_archivo
```

### **Ver los commits asociados a las tags**
```javascript
git show-ref --tags
```

## **Comparar la version del codigo - diff**
> Ver la comparacion de codigo del ultimo cambio guardado con **git add**
```javascript
git diff
```

> ver la comparacion del codigo de diferentes versiones
```javascript
git diff CommitA CommitB
```

## **Volver en el tiempo los commits - reset**

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

## **Ir a una version - checkout**
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

## **Fusion de ramas - merge**

> Fusionar la rama actual con la rama definida
```javascript
git merge Nombre_rama
```

> Fusionar la rama actual con la rama definida y poniendole un mensaje 
```javascript
git merge Nombre_rama -m "mensaje"
```

## **Remotos en git - remote**

### **Agregar al repositorio local un remoto que comunmente se llama 'origin' que apunta a una Url del repositorio remoto en Github**
```javascript
git remote add origin Url_repositorio
```

### **Ver los remotos existentes en el respotorio local**
```javascript
git remote
```

### **Ver el remoto de manera verbal(Nombre_remoto Url_repositorio)**
```javascript
git remote -v
```

### **Modificar la url del remoto**
```javascript
git remote set-url Nombre_remoto Url_remoto
```

## **Actualizar los cambios del repositorio - pull**

### **Actualizar los cambios del repositorio local con los del repositorio remoto**
```javascript
git pull Nombre_remoto Nombre_rama
```
> Por ejemplo tengo un remoto que lo llame "origin" y una rama que la llame "main"
> El commando de git seria el siguiente
> - git pull origin main

### **Actualizar los cambios del repositorio local con los del repositorio remoto(Forma forzada)**
```javascript
git pull Nombre_remoto Nombre_rama --allow-unrelated-histories
```

## **Alias en git - alias**
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

## **Tags en git y github - tag**

### **Ver las tags existentes**
```javascript
git tag
```

### **Agregar una tag con un nombre definido y un mensaje**
```javascript
git tag -a Tag_name -m "mensaje"
```

### **Eliminar una tag con nombre definido(No se eliminar del repositorio remoto)**
```javascript
git tag -d Tag_name
```

### **Eliminar tag del repositorio remotor definiendo la tag**
```javascript
git push origin :refs/tags/Tag_name
```

## **Clonar repositorio - clone**
> Clonar un respositorio remoto a uno local
```javascript
git clone Url_remoto
```

## **Ajustar los commits de una rama a otra - rebase**
```javascript
git rebase Nombre_rama
```
> Esto nos sirve en el caso que tengamos por ejemplo una rama **main** y una rama **experimento** al hacerle commit a la rama **experimento** y luego hacerle a la rama **main**
> La historia queda como ultimos commits de la rama 'main' al hacer **rebase** primero en **experimento** usando
```javascript
git rebase experimento
git rebase main
```
> y la rama **experimento* no hubiera entrado en los cambios realizados 
> - **OJO ESTO ES UNA MUY MALA PRACTICA**
> - **UTILIZAR SOLO EN LOCAL(repositorio local)**

## **Guardar cambios para despues - stash**

### **Agregar archivos en memoria para despues**
```javascript
git stash
```
> Cuando agregamos archivos con **git add** y debiamos agregarlo a otra rama diferente por error podemos dejarlo en espera la agregacion en memoria
> Cuando realizamos cambios y nos hemos equivocado usamos el comando para volver al ultimo commit
> - **Solo funciona si no has agregado**

### **Borrar los stash cuando no se necesitan**
```javascript
git stash drop
```

### **Ver listado de stash**
```javascript
git stash list
```

### **Volver al ultimo stash guardado**
```javascript
git stash pop
```

### **Movemos los cambios de la rama**
```javascript
git stash branch Nombre_rama
```

### **Limpiar y eliminar archivos copiados**
```javascript
git clean --dry-run
```
> - **Los archivos deben estar guardados**

### **Eliminar archivos copiados del repositorio local**
```javascript
git clean -f 
```

### **Traer commits viejos**
```javascript
git cherry-pick Tag_commit
```
> Nos traemos el commit con el tag definido, con esto podemos cojer el commit de otra rama y volverlo como si hubiera sido hecho por nuestra rama.
> Por ejemplo si tenemos la rama **main** y queremos traernos un commit de la rama **xyz** usamos el comando **cherry-pick** al hacer esto el commit definido por su **Tag** dejara de ser el commit de la rama **xyz** si no que sera el commit de la rama **main**
> - **ES UNA MUY MALA PRACTICA**

## Pull request

> Para subir cambios al fusionar a la rama principal por ejemplo **main** usando **PULL REQUEST**.
> Esto es una caracteristica de Github que permite que al fusionar una rama a la rama principal se tenga que llegar a confirmar la fusion o **merge**
> por el dueño del repositorio y/o contricullentes(Con o sin acceso)

> De esta forma la persona que quiere fusionar su rama con la principal tenga que esperar 
> una **CONFIRMACION** del dueño del repositorio o **PETICION_DE_CAMBIOS** para confirmar el merge


