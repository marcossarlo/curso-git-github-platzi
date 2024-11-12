# How fix
## Si cambiaste manualmente el nombre de un archivo
### con rm y mv
```bash
# de file-01.md a myfiles-01.md

# Agregar el archivo nuevo
git add myfiles-01.md

# Eliminar el archivo original
git rm file-01.md
git commit -m "Renombrado file-01.md a myfiles-01.md"
```

## Como renombrar un archivo
```bash
# Usa el comando git mv para renombrar
git mv file-01.md myfiles-01.md

# Usar git add -u
# para que Git actualice todos los cambios (seguimiento de archivos modificados y eliminados).
git add -u
git add myfiles-01.md
git commit -m "Renombrado file-01.md a myfiles-01.md"
```
