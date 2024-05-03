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

Git ofrece la posibilidad de crear una ramas.Estas se crean a partir de repositorios, las ramas nos permiten un trabajo en paralelo sobre un mismo codigo.

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
Empleamos el comando git merge para incorporar los cambios de una rama a la rama en la que nos encontramos en ese momento.
```python
git merge my-branch
```

Para poder eliminar una rama y asi tener un mejor manejo de las ramas. Se puede utilizar el el comando git branch con el parametro --delete o -d y en caso que quieras eliminar la rama que no ha sido fusionada previamente se debe utilizar el parametro -D.
```python
git branch -d nombre-rama
git branch -D nombre-rama
```