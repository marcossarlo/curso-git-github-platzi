# Volviendo en el Tiempo en Git

## GIT RESET --soft | --mixed | --hard
### Se enfoca en ajustar el historial de commits ya existentes en Git.

`git reset` se usa para "mover la rama actual" a un commit anterior en el historial y tiene tres modos principales que determinan qué partes (el área de staging y el directorio de trabajo) serán afectadas.

Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Se usa cuando quieres ajustar commits ya realizados en el historial de la rama, es decir, archivos que ya tienen un commit confirmado en el repositorio de Git.

El último commit desaparecerá del historial de commits.

Se usa cuando quieres ajustar commits ya realizados en el historial de la rama, es decir, archivos que ya tienen un commit confirmado en el repositorio de Git. Es útil para:

- Volver a un commit anterior en el historial (por ejemplo, cuando te arrepientes de uno o varios commits).
- Modificar el área de staging y/o el working directory dependiendo de la opción usada (`--soft`, `--mixed`, `--hard`).

```bash
$ git reset --soft HEAD~1 | $ git reset --soft hash-commit-específico
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# pero los cambios realizados en ese commit aún estarán listos para confirmar en el área de staging.
# Ideal si te das cuenta de que el último commit necesita ajustes y deseas volver a confirmar sin perder los cambios.
```


```bash
$ git reset HEAD~1
# git reset --mixed HEAD~1 es el comportamiento predeterminado de git reset.
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# y del último commit solo estarán en el Working Directory, sin estar en el Staging área.
# Útil si deseas revisar los cambios en el último commit antes de decidir qué hacer con ellos, ya que estarán fuera del área de staging.
```

```bash
$ git reset --hard HEAD~1
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# y todos los cambios del último commit serán eliminados completamente.
# Úsalo solo si estás seguro de que quieres descartar completamente el último commit y todos sus cambios.
```

## GIT RESTORE --source hashcommit | --staged
### Se enfoca en cambios sin confirmar, sin haber hecho commit
`git restore` permite revertir cambios en archivos específicos en el `Working Directory` o en el `Staging Area`. Este comando es más reciente y fue introducido para simplificar algunas tareas previamente realizadas con `checkout`.
- Descartar cambios en archivos específicos en el directorio de trabajo (volver a la última versión confirmada).
- Sacar archivos del área de staging sin perder los cambios en el directorio de trabajo.
- `--source <commit>`: Indica desde qué commit restaurar el archivo.
- `--staged`: Saca un archivo del área de staging.

```bash
# Quitar un Archivo del Área de Staging (Sin Perder Cambios):
git restore --staged file.md
# el archivo volverá al directorio de trabajo y saldrá del área de staging, por lo que no se incluirá en el próximo commit, pero los cambios no confirmados aún estarán presentes.
```

```bash
# Descartar Cambios en el Directorio de Trabajo:
git restore file.md | git restore archivo1.html archivo2.css archivo3.js
# Esto restaurará el archivo file.md a su última versión confirmada, descartando todos los cambios no guardados.
# Es como un ctrl-z
```

```bash
# Restaurar Desde un Commit Específico
git restore --source a1b2c3d ejemplo.html
# Esto restaurará ejemplo.html a la versión específica del commit a1b2c3d en el directorio de trabajo sin modificar el historial de la rama.
```

## GIT REVERT
### Crea un nuevo commit que deshace los cambios de un commit anterior específico
Esta es una opción preferida para mantener un historial de commits limpio, especialmente cuando trabajas en colaboración con otros.

Toma un commit específico y genera un nuevo commit que deshace todos los cambios introducidos por ese commit. La diferencia clave es que, a diferencia de reset y restore, revert no elimina el historial; en cambio, agrega un nuevo commit que revierte cambios.

Si trabajas en un proyecto con otros, revert es ideal, ya que no modifica el historial, evitando conflictos con otros miembros del equipo.

```bash
git revert 98e5a2a
```

## Diferencia Entre reset, revert, y restore
### reset
Modifica el historial moviendo el puntero de la rama actual hacia un commit anterior, eliminando los commits posteriores en el proceso. Es ideal para ajustes locales en el historial que no necesitas compartir.

### revert
Deshace los cambios de un commit específico creando un nuevo commit, sin modificar el historial. Es ideal para revertir cambios de manera segura en un proyecto colaborativo.

### restore
Administra el área de staging y el working directory sin tocar el historial de commits. Se usa para descartar o restaurar cambios locales no confirmados.

## GIT RM --cached --force
Para eliminar archivos del working directory (directorio de trabajo) y del repositorio Git (área de staging). Este comando es útil cuando deseas quitar un archivo tanto de tu proyecto local como de la versión almacenada en Git.

- El archivo eliminado aparecerá como "deleted" en el próximo commit.
- Eliminar archivos que ya no necesitas en tu proyecto y no quieres que aparezcan en futuros commits.
- Limpiar tu historial eliminando archivos grandes o innecesarios que fueron añadidos por error.
- Dejar de rastrear archivos pero mantenerlos localmente usando --cached.

```bash
$ git rm --cached config.json
# Añade config.json al archivo .gitignore para que Git lo ignore en el futuro.

$ git rm --force 05-volviendo-en-el-tiempo.html
# Elimina el archivo de Git y del disco duro. 
```