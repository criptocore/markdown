
# COMANDOS DE GITHUB 

## PARA ENLAZAR UNA PC CON LOS REPOSITORIOS REMOTOS

- git config --global user.email "coremanrique@gmail.com"  
- git config --global user.name "criptocore"


### Para verificar el usuario y correo que enlaza esta pc con el repo remoto:

- git config --global --list

### Para eliminar la configuración de usuario:

- git config --global --unset-all user.name  # Elimina user.name de git  
- git config --global --unset-all user.email # Elimina user.email de git


## PARA GUARDAR PROYECTO EN REPOSITORIO LOCAL

- git init           # Crea la rama principal y el repositorio local  
- git status         # Seguimiento de los archivos pendientes o no guardados  
- git add .          # Agrega los archivos nuevos o modificados en el directorio actual 
- git add --all      # Agrega todos los cambios: nuevos, modificados y eliminados  
- git commit -m "comentario" # Envía los archivos al repositorio local

## REESCRIBIR UN COMMIT CONSERVANDO AUTOR, FECHA Y OTROS METADATOS

- git add .
- git commit --amend --no-edit  --> (--no-edit --> asegura que el mensaje del commit original se conserve sin cambios)
- git push --force    --> si ya se habia hecho u push de este commit antes del amend. se necesita forzar el push al repositorio remoto


## ENLAZA REPOSITORIO LOCAL CON REPOSITORIO REMOTO (ENVÍA ARCHIVOS DE OTRA RAMA)

- git remote add origin https://enlace-del-repositorio-remoto
- git remote -v                # Verifica si están enlazados los repos locales y remotos
- git push -u origin master    # Envía los archivos locales al repo remoto
- git push --force origin main # Fuerza el envío a la rama principal


## CREACIÓN DE NUEVAS RAMAS

- git branch rama2                   --> Crea nueva rama
- git branch                         --> Ver todas las ramas
- git checkout (rama elegida)        --> Selecciona la rama para trabajar
- git branch -m master main          --> Cambia el nombre de master a main

### SUBIR NUEVA RAMA CREADA A REPOSITORIO (GITHUB)

- git add .
- git commit -m "Descripción de los cambios en la nueva rama"
- git push -u origin nombre_de_la_nueva_rama

## CLONAR REPOSITORIOS

- git clone https://enlace-del-repositorio-a-clonar
- git pull origin main       # Actualiza los archivos de la rama principal en el repo local
- git push origin main       # Envía los cambios del repo local al repo remoto
- git push --force origin main # Fuerza la subida de cambios locales al repo remoto


## RECUPERAR CUALQUIER RAMA CLONADA QUE TENGA NUESTRO REPOSITORIO REMOTO

- git branch -r            --> Muestra las ramas remotas disponibles en un proyecto
- git fetch --all          --> Descarga todas las ramas remotas pero no las muestra
- git branch -a            --> Lista todas las ramas locales y remotas
- git checkout nombre_de_la_rama --> Elige la rama donde deseas trabajar


## ELIMINAR RAMAS

- git branch -d (rama a eliminar)              --> Elimina una rama local
- git push origin --delete (rama a eliminar)   --> Elimina una rama remota


## ELIMINAR ARCHIVO DE CUALQUIER RAMA

- git rm -r (archivo a borrar)

## FUSIONAR RAMAS SECUNDARIAS CON RAMA PRINCIPAL O MASTER 

- git checkout main    --> Debemos estar en la rama principal
- git checkout main    --> Es recomendable que la rama main este actualizada
- git merge nombre_de_la_rama_secundaria  --> Fusiona la rama secundaria con la principal
- Resolver posibles conflictos (git add . y git commit)
- git push origin main --> Subir los cambios al repositorio remoto

- git merge --no-ff rama2    # Fusiona cambios manteniendo ambas ramas y commits


## TAGS

- git tag -a 0.0.1 fn1v3bn4 -m "release 0.0.1"  # Crea un tag
- git tag 1.0.0 -m "release 1.0.0"              # Crea otro tag
- git push --tags                               # Sube los tags al repo remoto
- git tag -d nombreTag                          # Borra un tag


## REGRESAR O RESETEAR A UN PUNTO ANTES DE UN MERGE O FUSIÓN

- git checkout c19b41d        # Ir al commit donde queremos volver
- git checkout master         # Regresar a la rama principal
- git reset --hard c19b41d    # Volver al commit seleccionado o su estado anterior


## VER COMMITS EN NÚMEROS Y EN FORMA GRÁFICA

- git log --oneline                    # Ver los commits como lista
- git log --oneline --all --graph      # Ver los commits en forma gráfica


## VER ARCHIVOS DE CADA RAMA

- dir

## CAMBIAR EL NOMBRE DE MASTER A MAIN

- git branch -m master main
- git config --global init.defaultBranch main  # Cambia la rama principal por defecto a main

---
## VIM (editor de texto)

> 1. Salir de Vim sin guardar cambios:
Si solo quieres salir sin hacer ningún commit ni guardar los cambios:

>Presiona Esc para asegurarte de que estás en el modo normal de Vim.
Escribe :q! y presiona Enter.
Esto forzará la salida sin guardar ningún cambio.

>2. Salir de Vim y guardar los cambios (realizar el commit):
>Si ya has resuelto los conflictos y deseas concluir el commit:

>Presiona Esc para entrar en el modo normal de Vim.
Escribe :wq y presiona Enter.
> Esto guardará los cambios y cerrará el editor, finalizando el commit.

## ¿Cómo cambiar el editor por defecto de Git? (para reemplazar vim)

>Si no te sientes cómodo usando Vim y prefieres otro editor, como Visual Studio Code, puedes configurarlo como editor por defecto en Git. Por ejemplo, para usar VS Code, puedes ejecutar este comando en Git Bash:

>Copiar código
git config --global core.editor "code --wait"

>Esto hará que cada vez que Git necesite que edites algo, abra Visual Studio Code en lugar de Vim.

