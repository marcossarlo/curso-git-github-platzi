# Gestión de versiones: tag y checkout
```https://platzi.com/home/clases/11059-gitgithub/71789-gestion-de-versiones-con-tag-y-checkout/```

## GIT TAG
Es un comando en Git que te permite marcar puntos específicos en el historial de tu repositorio con etiquetas (tags). Estas etiquetas son útiles para **señalar versiones importantes**, como lanzamientos de software (v1.0.0, v2.0.0, etc.), hitos del proyecto o cualquier commit que desees resaltar.
- Un tag es una referencia inmutable a un commit específico.
- Se usa comúnmente para versionar tu código, especialmente en el contexto de releases.
- A diferencia de las ramas, los tags no cambian; son solo marcadores permanentes.

### Tipos de Tags en Git
1. Tags Anotados (annotated):
    - Contienen un mensaje, el nombre del autor, la fecha, y están almacenados como un objeto completo en la base de datos de Git. 
2. Tags Ligeros (lightweight):
    - Son simplemente punteros a un commit, similares a una rama que no cambia.
    - No contienen información adicional (autor, fecha, mensaje).

```bash
git tag v1.0.0
# Tag Ligero (Lightweight): crea un tag llamado v1.0.0 que apunta al commit actual.

git tag -a v1.0.0 -m "Release version 1.0.0"
# -a: Indica que es un tag anotado.
# -m: Permite añadir un mensaje para describir el tag.

git tag -a v1.0.0 038f253fdebd32433d02da20f72e294f26bfb7df -m "Tag de versión 1.0.0"
# Crear un Tag Anotado en un Commit específico:

git tag
# Ver la Lista de Tags
git tag

git show v1.0.0
# Muestra detalles del commit asociado al tag y su mensaje

git tag -d v1.0.0
# Eliminar un Tag Localmente

git push origin --delete v1.0.0
# Eliminar un Tag en el Repositorio Remoto

```

### Publicar Tags en GitHub (o en otro repositorio remoto)
Por defecto, los tags no se envían automáticamente cuando haces un git push. Debes enviarlos manualmente:
```bash
git push origin v1.0.0
# Enviar un Tag Específico

git push origin --tags
# Esto enviará todos los tags que has creado localmente al repositorio remoto.

git ls-remote --tags origin
# Verifica que el tag está en GitHub o visita GitHub:
```

### Resúmen 
- Usa ```git tag -a <tagname> <commit-id> -m "<mensaje>"``` para un tag anotado.
- Usa ```git tag <tagname> <commit-id>``` para un tag ligero.
- Usa ```git push origin <tagname>``` para enviar el tag al repositorio remoto.
