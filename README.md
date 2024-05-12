# CURSOS DE GIT #
##  Clase I ##

#### ¿ Que es Git ?  ####
> Git es un control de versiones en un sistema que registra cada cambio que se realiza en el codigo fuente de un proyecto.

### COMANDOS ###
El comando git int se utiliza para crear un proyecto desde cero. Asi tambien creara una carpeta configurada con el nombre que has indicado.
```python
git init nuevo-proyecto
```
Con el git status se puede observar en el estado que se encuentra.
```python
git status
```
El git add es posible añadir algun archivo al area de staging pero no quieres grabarlo en el repositorio.
```pythom
git add nombre-archivo
```
##  Clase II ##
### Ramas y Merge ###
> Las ramas son una coleccion de directorios y archivos de repositorios. Cada vez que sea una rama, tambien se crea una copia de coleccion  de archivos.

> Git ofrece la posibilidad de crear una ramas.Estas se crean a partir de repositorios, las ramas nos permiten un trabajo en paralelo sobre un mismo codigo.

<img src= "https://miro.medium.com/v2/resize:fit:801/1*DhagidpZutkaCmAZobmzDQ.png"/>

### COMANDOS ###

El comando git branch nos permite crear, listar, renombrar y eliminar ramas .
```python
git branch nombre-rama
```
Para poder movernos por las ramas se puede utilizar el git switch.
```python
git switch nombre-rama 
```
```python
git checkout nombre-rama
```
Empleamos el comando git merge para incorporar los cambios de una rama a la rama en la que nos encontramos en ese momento.
```python
git merge my-branch
```

Para poder eliminar una rama y asi tener un mejor manejo de las ramas. Se puede utilizar el el comando git branch con el parametro --delete o -d y en caso que quieras eliminar la rama que no ha sido fusionada previamente se debe utilizar el parametro -D.
```python
git branch -d nombre-rama
git branch -D nombre-rama
```
#### CONFLICTOS ####
Un conflicto es una situaciom en la que Git no es capaz de determinar que cambio es el que tiene que prevalecer una vez ocurra una fusion.
Para solucionar el conflicto nos saldra tal como se ve en la figura.

<img src="https://www.netmentor.es/Imagen/f084cf7e-9650-4cf5-a893-7d993bffea6b.jpg"/>

En la parte superior se tiene el contenido que ya existia en la rama del destino. De la rama fusion(la rama main) y de la linea divisoria ======= tenemos el contenido de la rama origen (la rama changes) que queremos incorporar a la rama main. Para resolver el conflicto tenemos que decidir entre:

- Nos quedamos con los cambios de la rama **main**.
- Nos quedamos con los cambios de la rama **changes**.
- Modificamos cambios para hacer una fusion personalizada.

Ahora se puede fusionar los cambios de la rama **changes** a la rama **main** luego agregan los cambios y se hace un commit.
## Clase III ##
### GitHub ###
GitHub es un servicio de alojamiento en la nube de codigo fuente basado en el control de versiones que ofrece Git para manejar repositorios.

#### Repositorios Remotos ##
Son repositorios que estan hospedados en un servidor y que servira de punto de sincronizacion entre diferentes repositorios locales.
### Comandos ###
**Enlazar un repositorio local con un repositorio remoto :**
Para conectar nuestro repositorio local con el repositorio remoto debemos usar el comando git remote add y le pasamos dos parametros. primero pasamos en alias que le pondremos al repositorio remoto y el segundo seria la direccion del mismo repositorio.
```python
git remote add alias <direccion>
```
Para enviar los cambios del repositorio local al repositorio remoto. Para ello ejecutamos el siguiente comando.
```python
git push alias <rama>
```
**Clonar un repositorio remoto :**
Para clonar un repositorio remoto necesitamos saber su direccion. La direccion normalmente se encuentra en HTTPS o SSH.
Una vez obtenido la direccion es momento de utilizar el comando.
```python
git clone <direccion>
```
**Crer una rama remota :**
Si queremos crear una rama remota y cambiar al mismo instante a la rama creada utilizamos el siguiente comando.
```python
git switch -c nombre-rama
``` 
Para mandar o enviar la rama creada a nuestro repositorio remoto ejecutamos :
```python
git push alias-repositorio nombre-rama
```
**Actulizar nuevas ramas del GitHub:** Con el comando git fetch podemos actualizar la nuevas ramas que otro usuario envio al repositorio remoto y esa rama no aparece en tu repositorio se ejecuta el comando:
```python
git fetch
```
El comando git remote prune origin elimina las referencias locales que corresponden a ramas remotas que ya no existen en el repositorio remoto "origin". Esto asegura que tu copia local esté actualizada y no contenga referencias obsoletas que puedan causar confusión o problemas en el futuro. 

```python
git remote prune origin
```
## Clase IV ##
### Git Push  ##
Es un comando utilizado en git para enviar tus cambios locales a un repositorio remoto. Esto actuliaza el repositorio remoto con tus ultimos commits.
```python
git push alias nombre-rama
```
Si quieres subir todo los cambios al repositorio remoto con todo y sus ramas, puedes utilizar:
```python
git push --all origin
```
Cuando quieres ignorar o forzar los cambios locales hechos al repositorio Git en GitHub puedes usar el comando.
(Es una mala practica).
```python
git push --force origin nombre-rama
```
### Git pull ##
Es un comando para actualizar tu repositorio local con los cambios mas recientes del repositorio remoto.Lo que basicamente hace es descargar los cambios del repositorio remoto y los fusiona con tu rama local.

```python
git pull origin
```
Si quieres traer los cambios de una rama especifica se puede utilizar el siguiente comando:

```python
git pull origin nombre-rama
```
### Pull request ##
Una pull request es una solicitud de los cambios que ha realizado en su propia copia del repositorio se incorporen al repositorio principal. Esto permite a otros revisar los cambios, realizar comentarios y sugerir modificaciones antes de que se fusionen  con el repositorio principal.

Las pull request son muy importantes en el flujo de trabajo colaborativo en el desarrollo de software y son especialmente utiles en proyectos de codigo abierto.

## Clase V ##

### Git Flow

El git flow se basa en la creacion de ramas las cuales son: las ramas principales y ramas de apoyo.

**Ramas Principales**
Es las ramas principales estan la rama main o master y la rama develop.
<br>

<img src="https://wac-cdn.atlassian.com/dam/jcr:a13c18d6-94f3-4fc4-84fb-2b8f1b2fd339/01%20How%20it%20works.svg?cdnVersion=1719"/><br>
<br>

- **Main o Master :** Su proposito es almacenar el codigo que se encuentra en produccion.

- **Develop :** Es donde se almacena el codigo de pre-produccion con caracteristicas que todavia tienen que ser probadas y aprobadas para que se actualizen a la rama main.

**Ramas de Apoyo**
Es las ramas de apoyo estan la rama feature , release y hotfix.
<br>

<img src="https://wac-cdn.atlassian.com/dam/jcr:cc0b526e-adb7-4d45-874e-9bcea9898b4a/04%20Hotfix%20branches.svg?cdnVersion=1719" />
<br>

- **Feature :** Esta se crea a partir de la rama develop y una vez finalizan son fusionadas de nuevo en develop y eliminidas.<br>
Se utiliza para cuando se trabaja en una nueva caracteristica para el proyecto.

- **Release :** En estas ramas se puede seguir trabajando para añadir algun pequeño cambio de ultima hora o algun parche a un error que se haya detectado justo antes del lanzamiento.

- **Hotfix :** Esta rama se crea desde la rama main para solucionar problemas o cambios imprevistos.

### Ship / Show / Ask ###
Es una estrategia de ramas que combina la idea de crear pull request con la habilidad de seguir actulizando los cambios rapidamente.

- **Ship :** Esta rama se fusiona a la rama principal (main) sin previa revision.

- **Show :** Esta abre una solicitud de cambios que seran revisados por CI pero se fusiona inmediatamente despues de la revision.

- **Ask :** Esta abre un pull request para discutir los cambios antes de fusionarlo con la rama principal (main).

## Clase VI ##
### Buenas Practicas en Git ###
Hacer commits a menudo no significa que debas hacer commits sin sentido, guarda tus progresos pequeñas pero que tengan un significado y que no deje tu proyecto sin funcionar.

**Escrbir un buen commit**
Algunas palabras pueden ayudar a entender mejor el commit que deseas guardar y estos son los siguientes:
- **Add :** Significa que se añadira un nuevo archivo.
- **Change :** Significa que modificara un archivo existente.
- **Fix :** Significa que arreglo algun bug o error.
- **Remove :** Significa que se elimina un archivo.

En los commits tambien existen normas que no se deben hacer y veremos algunas:
- No usar punto final ni puntos suspensivos en tus mensajes.
- Usar como maximo 50 caracteres para tu mensaje en el commit.
- Añadir el contexto que sea necesario en el cuerpo del commit.

#### Usar prefijos para los commits 
Es necesario que existan ciertas reglas para que el historial sea legible.

**Prefijos**
- **feat** Para una nueva caracteristica del usuario.
- **fix** Para un bug que afecta al usuario.
- **perf** Para cambios que mejoran el rendimiento del sitio.
- **build** Para cambios en el sistema de build, tareas de despliegue o instalacion.
- **docs** Para cambios en la documentacion.
- **refactor** Para refactorizacion del codigo como cambios de nombre variables o funciones.
- **style** Para cambios de formato, tabulaciones, espacios o puntos y coma,etc.
- **test** Para test o refactorizacion de uno ya existente.

## Clase VII ##

### Deshacer Cambios ###

A veces queremos retirar el ultimo commit que hicimos por algun motivo como no era el momento hacer un commit o por que simplemente no era necesario hacer un commit.
Si aun no actulizaste los cambios al repositorio remoto tienes dos formas de hacer esto:

- Si quieres mantener los cambios
```python
git reset --soft HEAD~1
```
- Si No quieres mantener los cambios
```python
git reset hard HEAD~1
```
**Arreglar un commit :** se usa el siguiente comando para arreglar un commit, como cambiar el mensaje del commit.
```python
git commit --amend -m "Este es el mensaje correcto"
``` 

## Clase VIII ##
### Hooks ###
Un hook es un punto de enganche, es una posibilidad de ejecutar una accion.
Estos son parte del repositorio que los contiene y no se guardan ni se sincronizan con otras replicas del repositorio automaticamente.

**Crear un hook :** Para crear un hook tienes que crearun archivo nombre-hook en la carpeta .git/hooks y en el poner el codigo que  quieras que se ejecute.

### Alias ###
Los alias son mas para recordar o recortar un comando muy largo y poner algo mas simple y para eso se ejecuta el siguiente comando:
```python
git config --global alias.co "checkout"
```
### Trucos en Git ###
**Comandos**
- **Git stash :**  Nos sirve para movernos por las ramas cuando nos estanquemos en una parte del codigo.
```python
git stash
```
```python
git stash pop
```
**Git Cherry-pick :** El cherry-pick trae especificamente al commit que tu escojas mediante el id del commit.
```python
git cherry-pick id
```
**Git bisect:** Nos permite encontrar que commit a introducido algun error por que nosotros colocamos los diferentes bisect dependiendo lo que hace el commit en su monento.
```python
git bisect
```
```python
git bisect start
```
```python
git bisect bad
```
```python
git bisect good
```
```python
git bisect reset
```
Cada uno se coloca en el commit necesario por ejemplo si el commit genera algun error colocamos el **git bisect bad** y asi tambien con los otros git bisect.

