# Volviendo en el Tiempo en Git

## GIT RESET --soft | --mixed | --hard

`git reset` se usa para "mover la rama actual" a un commit anterior en el historial y tiene tres modos principales que determinan qué partes (el área de staging y el directorio de trabajo) serán afectadas:

El último commit desaparecerá del historial de commits.

Se usa cuando quieres ajustar commits ya realizados en el historial de la rama, es decir, archivos que ya tienen un commit confirmado en el repositorio de Git. Es útil para:

- Volver a un commit anterior en el historial (por ejemplo, cuando te arrepientes de uno o varios commits).
- Modificar el área de staging y/o el working directory dependiendo de la opción usada (`--soft`, `--mixed`, `--hard`).

```bash
$ git reset --soft HEAD~1 | $ git reset --soft hash-commit-específico
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# pero los cambios realizados en ese commit aún estarán listos para confirmar en el área de staging.
# Ideal si te das cuenta de que el último commit necesita ajustes y deseas volver a confirmar sin perder los cambios.

$ git reset HEAD~1
# git reset --mixed HEAD~1 es el comportamiento predeterminado de git reset.
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# y del último commit solo estarán en el Working Directory, sin estar en el Staging área.
# Útil si deseas revisar los cambios en el último commit antes de decidir qué hacer con ellos, ya que estarán fuera del área de staging.

$ git reset --hard HEAD~1
# HEAD se moverá al commit anterior, el último commit desaparecerá del historial, 
# y todos los cambios del último commit serán eliminados completamente.
# Úsalo solo si estás seguro de que quieres descartar completamente el último commit y todos sus cambios.
```

## GIT RESTORE --source hashcommit | --staged
`git restore` permite revertir cambios en archivos específicos en el `Working Directory` o en el `Staging Area`. Este comando es más reciente y fue introducido para simplificar algunas tareas previamente realizadas con `checkout`.
- Descartar cambios en archivos específicos en el directorio de trabajo (volver a la última versión confirmada).
- Sacar archivos del área de staging sin perder los cambios en el directorio de trabajo.
- `--source <commit>`: Indica desde qué commit restaurar el archivo.
- `--staged`git: Saca un archivo del área de staging.