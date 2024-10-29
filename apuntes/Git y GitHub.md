# GIT

## ¿Qué es GIT?

- Es un sistema de control de versiones distribuido. Esto significa que cada desarrollador tiene una copia completa del proyecto en su equipo, y del historial del proyecto.
- **Link**: [https://git-scm.com/](https://git-scm.com/)

## Configuración Inicial

```bash
# Nombre y Email
git config --global user.name "Tu Nombre"
git config --global user.email "ejemplo@gmail.com"

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

## Primeros pasos

### Inicializar un Repositorio

```bash
git init
```

### Agregar archivos al área de preparación

```bash
# Agregar un archivo
git add archivo.txt

# Agregar todos los archivos del directorio al área de preparación
git add .

# Mostrar información sobre el directorio de trabajo y el área de preparación
git status

# Remover un archivo del área de preparación (del commit)
git rm --cached archivo.txt

# Commit de archivos con mensaje incluido
git commit -m "mensaje con los cambios realizados"

# Commit de archivos con mensaje en editor de código
git commit

# Commit de archivos sin pasar por el área de preparación
git commit -a
```

### Git restore, checkout y  más

```bash
# Restaurar un archivo eliminado
git restore archivo.txt

# Restaura el archivo especificado al estado que tenía en el último commit
# git checkout solo funciona si no se ha hecho commit.
git checkout archivo.txt

# Renombrar un archivo
git mv nombre-actual.txt nombre-nuevo.txt

# Mejor alternativa a git status: Te muestra los archivos modificados
git status -s
```

---

## Resumen - Comandos Importantes

```bash
# Inicializar repositorio
git init

# Añadir archivos
git add . 
git add archivo.txt

# Ver el estado de los archivos
git status
git status -s

# Restaura el archivo especificado al estado que tenía en el último commit
git checkout archivo.txt
```