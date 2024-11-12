
> Fundamentos de Git y control de versiones:
# Cómo Resolver Conflictos de Ramas en Git
[https://platzi.com/home/clases/11059-gitgithub/71790-resolucion-de-conflictos-en-git/
](https://)

Resolver conflictos de ramas en Git es una parte esencial del control de versiones, especialmente cuando varios desarrolladores trabajan en el mismo proyecto. Los conflictos **suelen ocurrir cuando Git no puede fusionar automáticamente los cambios de dos ramas diferentes**.

Un conflicto surge cuando Git no puede decidir automáticamente cómo combinar los cambios entre dos ramas, *porque las mismas líneas de un archivo fueron modificadas en ambas ramas*.

Por ejemplo:
- Un archivo fue modificado en la rama main y también en la rama feature.
- Un archivo fue eliminado en una rama pero modificado en otra.

```bash
# Identificar Archivos en Conflicto
git status
    both modified: archivo.txt

# Resolver el Conflicto Manualmente: Decide qué cambios conservar:
# Puedes optar por mantener solo uno de los bloques, combinar ambos, o crear una nueva versión basada en los dos.

# Marcar el Archivo como Resuelto
git add archivo.txt

# Finalizar el Proceso de Fusión
git commit -m "Resuelto conflicto en archivo.txt"

# Abortar la Fusión
git merge --abort
```

## Consejos para Evitar y Manejar Conflictos
- Hacer Commits Frecuentes
- Mantén tu Rama Actualizada: asegúrate de que esté sincronizada con la rama main
- Usa Ramas para Nuevas Funcionalidades: Mantén el desarrollo de nuevas funcionalidades en ramas separadas (feature-branches).
- Comunicación en Equipo: Si trabajas en equipo, coordina con tus compañeros para evitar trabajar en los mismos archivos simultáneamente.
