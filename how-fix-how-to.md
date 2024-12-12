# How fix
## Si cambiaste manualmente el nombre de un archivo
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
## Como Abrir Editor GitHub.dev
Estando en un repositorio de GitHub, presionar ```.``` 

## You have divergent branches and need to specify how to reconcile them."
### Problema: 
Cuando hice un: ```git pull origin main``` me salió el siguiente mensaje:

"hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint:
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint:
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches."

No se tenga que ver que en el repositorio remoto no tenia los últimos cambios del repositorio local, además hice unos cambios en el repositorio remoto.
Luego de ello hice el git pull origin main y me salió el mensaje anterior.

### Solución
```bash
git config pull.rebase false
# Merge (Fusionar):
# Crea un nuevo commit de merge que combina los cambios de ambas ramas
# Preserva todo el historial de commits

git pull origin main
# Se abrío Nano y pusimos el mensaje del commit
```