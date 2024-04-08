# apuntesGIT
Apuntes de git

Arrancar con Git
$ git config --global user.name "NOMBRE DE USUARIO"
$ git config --global user.mail "EMAIL DE USUIARIO"
Esto crea un archivo dentro del usuario con esos datos.

GIT INIT
Inicializa Git en la caperta deseada (dentro de la carpeta en la que se este), se crea una carpeta oculta ".git" 
$ git init


GIT STATUS
para ver el estado de la carpeta.
$ git STATUS
Te va a mostrar el estado de lo que esta en stage y lo que no, si falta realizar commit o si ya esta todo actualizado. Diferencia preparado de no preparado y lo ya se realizo commit
$ git status -sb -> es un modo resumido del statis Primera columna lo que ya esta agregado, segunda columna lo que no esta agregado. 
“R ” - has been renamed, and that rename has been staged.
“A ” -  is a newly added file.
“ D” - has been deleted, but the deletion is not staged.
“MM” - some changes in "archivo" have been staged, and some have not.
“UU” - there are unresolved merge conflicts in "archivo"
“??” - is an untracked file.

GIT ADD
agregar cosas para las "fotografias" antes de hacer el commit. Por ejemplo agregar un archivo
$ git add PruebaGit.py
$ git add . agrega todos los ficheros
El add tambien agrega las ultiams modificaciones de archivos para el area de stage.


GIT commit
Saca la fotografia
$ git commit
Al momento de dar el commit te va a pedir un comentario
y te da dactos con respecto a como esta el commit, donde agrega y que va a agregar en el commit
$ git commit -m "MENSAJE PARA DEJAR" (forma mas rapida).
Como hacer un commit y que actualice lo ultimo que tenemos en stage desactualizado. 
$ git commit -a-m "mensaje".
Esto agrega al commit las ultimas modificaciones de archivo. NO TIENE EN CUENTA LOS ARCHIVOS QUE NO FUERON AGREGADOS 

GIT COMMIT --AMEND
sirve para cuando te equivocas en el commit para reemplazarlo por uno nuevo, ejemplo, para cambiar el mensaje del commit o bien porque te olvidaste de poner algun archivo en preparacion


GIT LOG
Muestra información sobre los commit
$ git log 
$ git log --graph muesta un grafico
CREAR UN ALIAS
$ git config --global alias.tree(este el el alias) "log --graph"
SI yo llamo "$ git tree" me atre ese alias. Ese datos se guardan en el archivo git config.
Forma de ver bien el log
$ git log --pretty=format:"%h %s" --graph
$ git log --oneline

GIT CHECKOUT
Posicionarse en otra fotografia de git
$ git CHECKOUT "Comandos de git.txt"
$ git CHECKOUT PruebaGit.py
Vuevle a la ultima foto sacada

HEAD
Cual es la rama principal o cual es la importante
podemos ir con el CHECKOUTa otra rama y si marcamos "$ git checkout HEAD" pone como cabecera esa rama, sive tambien para marcar donde estas parado.

GIT IGNORE
Crear archivos o "ficheros" que git no queremos que tenga en cuenta se detallan ".gitignore"
dentro de este pondremos los ficheros que uqeremos que git IGNORE
**/.comando de git
De igual manera el status va a tirar que falta pero solo ese archivo.

GIT RM
Para borrar archivos. 
con el RM (remove) borramos archivos.
$ git rm "nombre" -> borra el archivo dle stage y del directorio
$git rm -cached -> borra el archivo del stage pero NO del directrio

GIT MV 
Cambia el nombre de un archivo, esto funciona en 3 niveles(cambia el nombre hace un rm del archivo original y hace un add del nuevo archivo con nombre)=
$ git mv "nombre original" "nuevo nombre".

Git DIFF
Nos muestra en consola los cambios que se realizaron desde elñ ultimo commit
$ git DIFF
En realidad segun la doc oficial el DIFF diferencia entre lo ultimo que esta en stage y lo que no, lo agregado de lo que no.
Para ver la diferencia entre el ultimo commit y lo que esta en stage es
$ git diff --stage

>Git reset y git reset hard
sirve para situarse en lugares de tiempo
$ git reset --hard "el id del commit que queremos volver"
esto borra todos lso commmit anteriores.
El git reset también ayuda a sacar quitar un archivo modificado de la zona de preparación
 
GIT REFLOG
Historial completo de interacciones. Si borras algo podemos recuperarlo

Si borramos algo con git reset --hard podemos volvar con el mismo reset a los commit borrados

Git TAG
Para colocar un tag en el commit
$ git tag -> para ver los tag
$ git tag "nombredel tag" (sin espacios0)
$ git checkout tags/"nombre"

GIT BRANCH
Crea nuevas ramas en las cuales trabajar
$ git branch "nombre de la rama"
Crear el branch no te mueve a esa rama
$ Git checkout -b hotfix -> Crea una rama y te mueve a esa posicion
	Es lo mismo que $ git branch "hotfix"
			$ git cheackout hotfix
Borrar rama que ya se merge
$ git branch -d hotfix


GIT switch
Te mueve a esa rama
$ git switch "nombre de la rama"
el swtich necesitas tener descarda la rama para poder pasar, en cambio el ckeckout la descarga

GIT MERGE
Combinar los cambios entre ramas. se pone la rama que va a unirse a la que estoy
$ git merge "la rama" 
$ git merge main/master.
se tiene que poner algun mensaje como el commit

GIT stash
sirve para almacenar temporalmente cambios sin commit si queres irte a otra rama o demas, de esta forma no es necesarios realizar un ADD y commit
$ git stash
para ver las cosas guardadas
$ git stash list
PARA RECUPERAR (CARGAR LO GUARDADO)
$ git stash pop
Para eliminar el stash
$ git stash drop

GIT fetch
Se descarga el historial de cambios de Github que no estan en tu ordenador

GIT PULL 
descarga los cambios
Cuando hay acambios que no tienes que necesitas tenerlos puede ser que esten en dos ramas distintas, recomienda hacer un Merge (sin rebase)
$ git config pull.rebase false ->traer los cambios. Se puede poenr la rama que queire traer
$ git pull


Git PUSH 
Sube los nuevos cambios

Alias para comandos
$ git config --global alias.co	checkout
$ git config --global alias.br	branch
$ git config --global alias.ci	commit
$ git config --global alias.st	status

https://training.github.com/downloads/es_ES/github-git-cheat-sheet/
