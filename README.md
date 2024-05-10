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
git checkout nombre-rama
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

- **Main o Master :** Su proposito es almacenar el codigo que se encuentra en produccion.

- **Develop :** Es donde se almacena el codigo de pre-produccion con caracteristicas que todavia tienen que ser probadas y aprobadas para que se actualizen a la rama main.

**Ramas de Apoyo**
Es las ramas de apoyo estan la rama feature , release y hotfix.

- **Feature :** Esta se crea a partir de la rama develop y una vez finalizan son fusionadas de nuevo en **develop** y eliminidas.<br>
Se utiliza para cuando se trabaja en una nueva caracteristica para el proyecto.

- **Release :** En estas ramas se puede seguir trabajando para añadir algun pequeño cambio de ultima hora o algun parche a un error que se haya detectado justo antes del lanzamiento.

- **Hotfix :** Esta rama se crea desde la rama main para solucionar problemas o cambios imprevistos.





