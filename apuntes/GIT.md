# GIT

## ¿Qué es GIT?

- Es un sistema de control de versiones distribuido. Esto significa que cada desarrollador tiene una copia completa del proyecto en su equipo, y del historial del proyecto.
- **Link**: [https://git-scm.com/](https://git-scm.com/)

## Configuración Inicial

```bash
# Nombre y Email
git config --global user.name "Juan Bautista Malina"
git config --global user.email "malinajuanbautista@gmail.com"

# Editor de Código: Visual Studio Code
git config --global core.editor "code --wait"

# Habilitar Colorización
git config --global color.ui true

# Configuración para los carácteres de salto de línea
git config --global core.autocrlf true # WINDOWS
git config --global core.autocrlf input # MAC Y LINUX

# Listar las configuraciones
git config --list 
```

## Comandos Iniciales

```bash
# NOTA: filename hace referencia al nombre del archivo en cuestión.

# Iniciar un repositorio
git init

# Agregar un archivo al staging area o área de preparación
git add archivo.txt

# Agregar todos los archivos del directorio al staging area
git add .

# Mostrar información sobre el directorio de trabajo y el área de preparación
git status

# Mostrar información resumida
git status -s 

# Commit de archivos con mensaje incluido
git commit -m "mensaje con los cambios realizados"

# Commit de archivos con mensaje en editor de código
git commit

# Commit sin pasar por el staging area
git commit -am "mensaje"

# Listar el historial de commits
git log

# Listar los commits en una sola línea
git log --oneline

# Visualizar los cambios realizados en un commit determinado
git show id-commit

# Visualizar el contenido de un archivo, dentro de un commit en específico
git show id-commit:filename

# Listar archivos y/o directorios de un commit en específico
git ls-tree id-commit

# Quitar archivos del staging area
git restore --staged filename

# ------------
# Ignorar archivos y directorios: Crear archivo ***.gitignore***
# Dentro del archivo, añadir los diferentes archivos y carpetas a ignorar.
#
# Ignorar archivos y directorios que ya hayan sido añadidos al repositorio:
# 1. Agregar la ruta del archivo o carpeta al .gitignore
# 2. Ejecutar el siguiente comando, para quitar el archivo del staged area
git rm --cached archivo.txt 
# ------------

# Mostrar los cambios realizados (antes de hacer commit)
git diff --cached

# Configurar vscode para ser utilizado como difftool
git config --global diff.tool vscode
git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'

# Mostrar visualmente cambios que se encuentran en el directorio de trabajo
git difftool

# Mostrar visualmente cambios que se encuentran en el staged area
git difftool --staged

# Descartar un archivo del staged area
git restore --staged filename

# Descartar cambios (eliminar cambios) de un archivo del directorio de trabajo
git restore filename

# Restaurar archivos a versiones anteriores (volver a un commit anterior)
# Opción 1: --source id-commit 
# Opción 2: HEADHEAD~(num contando desde el commit actual hacia atrás) filename
git restore --source=HEAD~1 filename

```

## Explorando el historial

```bash
# Mostrar los cambios introducidos en cada commit (cambios agregados y quitados)
git log --patch 

# Mostrar los archivos que cambiaron, y cuántas fueron las inserciones 
git log --stat

# Listar los commits en una sola línea y de manera resumida
git log --oneline

# Listar n commits (n = número)
git log --oneline -n

# Listar los commits de un autor en específico
git log --oneline --author="Juan"

# Listar los commits realizados desde una fecha en específico hacia el futuro
git log --oneline --after="aaaa-mm-dd"

# Listar los commits realizados desde una fecha en específico hacia el pasado
git log --oneline --before="aaaa-mm-dd"

# Listar los commits que incluyan archivos con un contenido en específico
git log --onelne -S"contenido del archivo"

# Listar commits que incluyan archivos con contenido en específico + cambios introducidos
git log --onelne -S"contenido del archivo" --patch

# Listar los archivos que cambiaron en los commits con un contenido específico
git log --oneline -S"contenido del archivo" --stat

# Buscar un commit por su mensaje
git log --oneline --grep="Mensaje del commit"

# Buscar commits por un rango (id contando desde el inicio, y luego el más reciente)
git log --oneline id-commit-abajo..id-commit-arriba

# Listar todos los commits que cambiaron un archivo en específico
git log --oneline (comandos extra aquí) -- filename

# ------------------------------------------
# Crear alias
git config --global alias.alias-personalizado "comando a asociar con el alias"

# Ejemplos de creación de alias
git config --global alias.gl "log --oneline --graph"
git gl # Uso del alias

git config --global alias.discard "restore ."
git discard

git config --global alias.unstage "restore --staged ."
git unstage
# ------------------------------------------

# Mostrar el nombre de los archivos que fueron modificados en un commit en específico
git show id-commit --name-status

# Mostrar diferencias entre dos commits en específico
git diff id-commit id-commit

# Mostrar diferencias de un archivo entre dos commits en específico
git diff id-commit id-commit filename

# Ir a un commit del pasado únicamente para hacer pruebas (NO EDITAR ARCHIVOS)
git checkout id-commit

# Regresar el puntero HEAD al commit actual (main)
git checkout main

# Mostrar las diferentes personas que contribuyeron en los distintos commits
git shortlog

# Mostrar el historial de un archivo en específico
git log --oneline filename

# Restaurar archivos eliminados de un commit anterior
git checkout id-commit filename

# Mostrar el autor de una línea en específico
git blame filename

# Mostrar el email del autor de una lónea en específico
git blame -e filename

# Mostrar un rango de líneas específicas de un archivo y el autor de ellas
# a: Se refiere a la línea desde la que se inicia.
# b: Se refiere a la línea donde termina el rango.
git blame -L a,b filename

# Colocar etiqueta de versionado a los commits
# tagname: Es el nombre que el usuario le va a dar a la etiqueta
git tag tagname id-commit

# Listar etiquetas
git tag

# Colocar etiqueta de versionado y una descripción
git tag -a tagname -m "Descripción"

# Listar etiquetas y mensajes
git tag -n

# ------------------------------------------
# Encontrando bugs con bisect:
# - Es necesario reconocer 1 commit bueno y 1 commit malo en el repositorio
# git bisect start: Iniciar el análisis
# git bisect bad id-bad-commit
# git bisect good id-good-commit
# Una vez en el modo "BISECTING" utilizar git bisect bad, o git bisect good, para 
# descartar y reducir la búsqueda a los commits, según sean buenos (sin errores), o malos
# (con errores).

# Detener bisect (detener escaneo de errores)
git bisect reset
# ------------------------------------------
```

## Gestión de ramas

```bash
# Crear una nueva rama
git branch nombre-rama

# Convenciones para los nombres de rama, ejemplos:
# - feature/carro-de-compra
# - bugfix/carro-de-compra

# Listar las ramas de un repositorio
git branch

# Cambiar de rama
git switch nombre-rama

# Renombrar una rama
git branch -m nombre-rama nuevo-nombre-rama

# Listar todos los commits de todas las ramas
git log --oneline --all

# Eliminar una rama
git branch -d nombre-rama

# Comparar commits entre ramas
git log rama1..rama2
git log main..feature/carro-de-compras # Ejemplo

# Comparar cambios entre ramas
git diff rama1..rama2
```