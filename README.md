# Curso Profesional de Git y GitHub / platzi
Instruido por:Freddy Vega

***********************************************
## 2. Comandos básicos en Git
***********************************************

### Configuraciones Guardadas:
```sh
# Ver configuracion
	git config --list --show-origin

# Establecer identidad
	git config --global user.name "John Doe"
	git config --global user.email johndoe@example.com

# Ver cambios
	git log
```

HEAD: Version mas reciente 
master: Rama master
HEAD -> master


### Analizar cambios en los archivos de tu proyecto con Git
```sh
git show
git diff <hash>
git diff <hash-version-vieja> <hash-version-nueva>
```

### Volver en el tiempo en nuestro repositorio utilizando reset y checkout


### Volver al pasado de una manera agresiva sin posiblidad de volver al futuro "Borramos la historia"
```
git reset --hard
git reset --soft
```

Cambios especificos a partir del commit
```
git log --stat
```

Permite volver en el tiempo con la posibilidad de volver al fututo conservando los cambios
```
git checkout <hash>
```

sacar archivos del área de Staging. No para borrarlos:
```
git reset HEAD
```

[Git reset vs. Git rm](https://platzi.com/clases/1557-git-github/23295-git-reset-vs-git-rm/)


***********************************************
## 3. Flujo de trabajo básico en Git
***********************************************

```
git commit -am "mensaje confirmacion"
```

Dejar de seguir un archivo:

```sh
git rm --cached <filename>
git rm --cached <directory>/*
```

## 4. Trabajando con repositorios remotos en GitHub

- Renombrar una rama

```sh
git branch -M <name_branch>
```

- Creacion de un repo en github

```sh
echo "# platzi-github" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/cristhi21/platzi-github.git
git push -u origin main
```

***********************************************
## 18. Uso de GitHub
***********************************************
- git fetch
- git merge
- git pull origin master

Clonar repositorio:
```
	git clone "URL"
```
Conectar el repositorio de GitHub con nuestro repositorio local:
```
	git remote add origin "URL"
```
Verificar que la URL se haya guardado correctamente:
```
	git remote
	git remote -v
```
Forzar un pull 
```
	git pull origin master --allow-unrelated-hitories
```
Guardar cambios de nuestro repositorio local en GitHub:
```
	git push origin master
```



***********************************************
## 19. Cómo funcionan las llaves públicas y privadas
***********************************************
- [Cómo funciona la criptografía](https://www.youtube.com/watch?v=Q8K311s7EiM)
- [¿Qué es la criptografía asimétrica?](https://es.cointelegraph.com/explained/what-is-asymmetric-cryptography)
- [Crear una clave SSH en Git y vincular en tu cuenta de Github](https://nancyzitle.medium.com/crear-una-clave-ssh-en-git-y-vincular-en-tu-cuenta-de-github-e7a6b22bc93f)


***********************************************
## 22. Tags y versiones en Git y GitHub
***********************************************
```
git log --all --graph --decorate --oneline
```

### ALIAS
alias arbolito="git log --all --graph --decorate --oneline"
arbolito

Los tags o etiquetas nos permiten asignar versiones a los commits con cambios más importantes o significativos de nuestro proyecto.

Comandos para trabajar con etiquetas:

- Crear un nuevo tag y asignarlo a un commit: 
```	
	git tag -a nombre-del-tag id-del-commit.
```
- Borrar un tag en el repositorio local: 
```
	git tag -d nombre-del-tag.
```
- Listar los tags de nuestro repositorio local: 
```
	git tag o git show-ref --tags.
```
- Publicar un tag en el repositorio remoto: 
```
	git push origin --tags.
```
- Borrar un tag del repositorio remoto: 
```
	git tag -d nombre-del-tag y 
	git push origin :refs/tags/nombre-del-tag.
```


***********************************************
## 23. Manejo de ramas en GitHub
***********************************************
Puedes trabajar con ramas que nunca envías a GitHub, así como pueden haber ramas importantes en GitHub que nunca usas en el repositorio local. Lo importante es que aprendas a manejarlas para trabajar profesionalmente.

- Crear una rama en el repositorio local: 
```
	git branch nombre-de-la-rama o git checkout -b nombre-de-la-rama.
```
- Publicar una rama local al repositorio remoto: 
```
	git push origin nombre-de-la-rama.
```
- Recuerda que podemos ver gráficamente nuestro entorno y flujo de trabajo local con Git usando el comando:
```
	gitk
```
- Publicar todas la ramas en el remoto
```
git push --all origin

sudo apt install gitk
```

***********************************************
## 24. Configurar múltiples colaboradores en un repositorio de GitHub
***********************************************

Solo debemos entrar a la configuración de colaboradores de nuestro proyecto (Repositorio > Settings > Collaborators) y añadir el email o username de los nuevos colaboradores.



***********************************************
## 25. Flujo de trabajo profesional: Haciendo merge de ramas de desarrollo a master
***********************************************
No es recomendable agregar archivos binarios al repositorio porque se vuelve muy pesado, ej imagenes

### Limpiar cache
ctrl + shift + R


***********************************************
## 26. Flujo de trabajo profesional con Pull requests
***********************************************
En un entorno profesional normalmente se bloquea la rama master, y para enviar código a dicha rama pasa por un code review y luego de su aprobación se unen códigos con los llamados merge request.

Para realizar pruebas enviamos el código a servidores que normalmente los llamamos staging develop (servidores de pruebas) luego de que se realizan las pruebas pertinentes tanto de código como de la aplicación estos pasan a el servidor de producción con el ya antes mencionado merge request.



***********************************************
## 33. Tu sitio web público con GitHub Pages
***********************************************

GitHub tiene un servicio de hosting gratis llamado **GitHub Pages**, tu puedes tener un repositorio donde el contenido del repositorio se vaya a GitHub y se vea online.


1. Crear un proyecto con el nombre del usuario
2. Luego de hacer push con todo ir a la siguiente url
```
nombre_usuario.github.io
```
3. Ir a settings y en la opcion githubpages -> seleeccionar rama master branch

cambiar nombre a nombre_usuario.github.io

-----------------------------------------------
-----MULTIPLES ENTORNOS DE TRABAJO EN GIT------
-----------------------------------------------

***********************************************
## 34. Git Rebase: reorganizando el trabajo realizado
***********************************************
Rebase reescribe la historia del repositorio y es solo para cambios locales

El comando rebase es una mala práctica, nunca se debe usar, pero para efectos del curso te lo vamos a enseñar para que hagas tus propios experimentos. Con rebase puedes recoger todos los cambios confirmados en una rama y ponerlos sobre otra.

# Cambiamos a la rama que queremos traer los cambios
- git checkout experiment

# Aplicamos rebase para traer los cambios de la rama que queremos 
- git rebase master




Git Rebase: reorganizando el trabajo realizado

Cambios silenciosos en otras ramas y pegar la hisgoria en otra rama.

Primero se debe hacer rebase a la rama que cambia
Por ultimo a la rama final


> Nota: tener en cuenta la historia de las 2 ramas por eso primero una, luego la otra.


No queda historia
quien hizo que?

si la rama master avanzo mucho ojo con los conflictos


rebase reescribe la historia del repositorio, cambia la historia de donde comenzó la rama y solo debe ser usado de manera local.



- git checkout -
cambia del actual branch al anterior branch en el que hubieran estado


***********************************************
## 35. Git Stash: Guardar cambios en memoria y recuperarlos después
***********************************************
**git stash** es típico cuando estamos cambios que no merecen una rama o no merecen un rebase si no simplemente estamos probando algo y luego quieres volver rápidamente a tu versión anterior la cual es la correcta

wip: work in prosgress

- **gitk**: muestra toda las historia

- git stash
El comando git stash guarda el trabajo actual del Staging en una lista diseñada para ser temporal llamada Stash, para que pueda ser recuperado en el futuro.
Para agregar los cambios al stash se utiliza el comando:

```
git stash
git stash save "mensaje identificador del elemento del stashed"
```

- Obtener elelmentos del stash
```
git stash pop
git stash pop stash@{<num_stash>}
```

- Listado de elementos en el stash
```
git stash list
```


- Crear una rama con el stash
Para crear una rama y aplicar el stash mas reciente podemos utilizar el comando
```
git stash branch <nombre_de_la_rama>
```

Si deseas crear una rama y aplicar un stash específico (obtenido desde git stash list) puedes utilizar el comando:
```
git stash branch nombre_de_rama stash@{<num_stash>}
```

- Eliminar elementos del stash

Para eliminar los cambios más recientes dentro del stash (el elemento 0), podemos utilizar el comando:
```
git stash drop
```

Pero si en cambio conoces el índice del stash que quieres borrar (mediante git stash list) puedes utilizar el comando:
```
git stash drop stash@{<num_stash>}
```
> Donde el <num_stash> es el índice del cambio guardado.

Si en cambio deseas eliminar todos los elementos del stash, puedes utilizar:
```
git stash clear
```

git stash : Guarda el trabajo actual de manera temporal. (Archivos modificados o eliminados)
git stash -u : Crea un stash con todos los archivos. (Añadiendo los creados Untracked)
git stash save “mensaje” : Crea un stash con el mensaje especificado.
git stash list : Permite visualizar todos los stash existentes.
git stash clear : Elimina todos los stash existentes.
git stash drop : Elimina el stash más reciente. El que tiene num_stash=0.
git stash drop stash@{num_stash} : Elimina un stash específico.
git stash apply : Aplica el stash más reciente. El que tiene num_stash=0.
git stash apply stash@{num_stash} : Aplica los cambios de un stash específico.
git stash pop : Aplica el stash más reciente y lo elimina. El que tiene num_stash=0.
git stash pop stash@{num_stash} : Aplica los cambios de un stash específico y elimina lo stash.
git stash branch nombre_de_rama : Crea una rama y aplica el stash mas reciente.
git stash branch nombre_de_rama stash@{num_stash} : Crea una rama y aplica el stash especificado.

### Consideraciones:

El cambio más reciente (al crear un stash) SIEMPRE recibe el valor 0 y los que estaban antes aumentan su valor.
Al crear un stash tomará los archivos que han sido modificados y eliminados. Para que tome un archivo creado es necesario agregarlo al Staging Area con git add [nombre_archivo] con la intención de que git tenga un seguimiento de ese archivo, o también utilizando el comando git stash -u.
Al aplicar un stash este no se elimina, es buena práctica eliminarlo.




**********************************************************
## 36. Git Clean: limpiar tu proyecto de archivos no deseados
**********************************************************

A veces creamos archivos cuando estamos realizando nuestro proyecto que realmente no forman parte de nuestro directorio de trabajo, que no se deberían agregar y lo sabemos.

Para saber qué archivos vamos a borrar tecleamos git clean --dry-run
Para borrar todos los archivos listados (que no son carpetas) tecleamos git clean -f

```
git clean --dry-run
git clean -f
```

**********************************************************
## 37. Git cherry-pick: traer commits viejos al head de un branch
**********************************************************

git cherr-pick <hash>




-----------------------------------------------
---- COMANDOS DE GIT PARA CASOS DE EMERGENCIA
-----------------------------------------------
**********************************************************
## 38. Reconstruir commits en Git con amend
**********************************************************

A veces hacemos un commit, pero resulta que no queríamos mandarlo porque faltaba algo más. Utilizamos git commit --amend, amend en inglés es remendar y lo que hará es que los cambios que hicimos nos los agregará al commit anterior.

```
git commit --amend
git commit --amend --no-edit
```

**********************************************************
## 39. Git Reset y Reflog: úsese en caso de emergencia
**********************************************************

Git Reset y Reflog: úsese en caso de emergencia

¿Qué pasa cuando todo se rompe y no sabemos qué está pasando? Con git reset HashDelHEAD nos devolveremos al estado en que el proyecto funcionaba.

```
git reset --soft HashDelHEAD te mantiene lo que tengas en staging ahí.
git reset --hard HashDelHEAD resetea absolutamente todo incluyendo lo que tengas en staging.
git reset es una mala práctica, no deberías usarlo en ningún momento; debe ser nuestro último recurso.
```



git reflog

**********************************************************
## 40. Buscar en archivos y commits de Git con Grep y log
**********************************************************
A medida que nuestro proyecto se hace grande vamos a querer buscar ciertas cosas.

Por ejemplo: ¿cuántas veces en nuestro proyecto utilizamos la palabra color?

Para buscar utilizamos el comando git grep color y nos buscará en todo el proyecto los archivos en donde está la palabra color.

Con git grep -n color nos saldrá un output el cual nos dirá en qué línea está lo que estamos buscando.
Con git grep -c color nos saldrá un output el cual nos dirá cuántas veces se repite esa palabra y en qué archivo.
Si queremos buscar cuántas veces utilizamos un atributo de HTML lo hacemos con git grep -c "<p>".

grep –> Para buscar en los archivos
log --> Para buscar en los commits.


Comando para buscar en los archivos y en los logs

git grep color -->Cuántas veces use la palabra color
git grep la --> Donde use la palabra la
git grep -n color–> En qué líneas use la palabra color
git grep -n platzi --> En qué lineas use la palabra platzi
git grep -c la --> Cuántas veces use la palabra la
git grep -c paltzi --> Cuántas veces use la palabra platzi
git grep -c “<p>”–> Cuántas veces use la etiqueta <p>


git log-S “cabecera” --> Cuántas veces use la palabra cabecera en todos los commits.


> NOTA: Esto es para administracion del proyecto.



**********************************************************
## 41. Comandos y recursos colaborativos en Git y GitHub
**********************************************************
[Git Blame](https://git-scm.com/docs/git-blame)

git shortlog -sn = muestra cuantos commit han hecho cada miembros del equipo.
git shortlog -sn --all = muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
git shortlog -sn --all --no-merge = muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
git blame ARCHIVO = muestra quien hizo cada cosa linea por linea
git COMANDO --help = muestra como funciona el comando.
git blame ARCHIVO -Llinea_inicial,linea_final= muestra quien hizo cada cosa linea por linea indicándole desde que linea ver ejemplo -L35,50
**git branch -r **= se muestran todas las ramas remotas
git branch -a = se muestran todas las ramas tanto locales como remotas




Ver quien modifico que cosa y en donde:

-c es opcional, solo es para formateo

Ver ramas remotas:
```sh
git branch -r
git branch -a : en blanco las locales y en rojo las remotas
```

Git-hub insights
- git blame css/estilos.css -L35,53 -c



**********************************************************
## 42. Tu futuro con Git y GitHub
**********************************************************
Travis, probar para configurar la conexion entre un repo y un servidor
jenkins es mas avanzado

Git lab puede correr en nuestro propio server o en nube

- [curso de jenkins](https://platzi.com/cursos/jenkins-basico/)
- Curso de Azure Paas
- [curso de Azure iaas](https://platzi.com/cursos/azure-iaas/)
- [Curso de devops con gitlab](https://platzi.com/cursos/gitlab/)
- [Curso profesional de devops](https://platzi.com/cursos/devops/)



Tu futuro con Git y GitHub
¡Felicitaciones por terminar el Curso profesional de Git y GitHub!

Aprendimos cómo usar Git y GitHub, hacer merge request, investigar quién hizo qué a través de la línea de comandos, cómo utilizar GitHub Pages, cómo revertir cambios y mucho más. Ahora queda de tu parte experimentar, fallar, subir, borrar y por último hacer deploy de tu proyecto y compartirlo con la comunidad.

Recuerda resolver los ejercicios, completar el examen, darle 5 estrellas al profesor y compartir tu proyecto, notas, todas tus dudas y comentarios en la sección de discusiones.
