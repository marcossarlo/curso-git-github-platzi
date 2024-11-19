> Introducción a GitHub
# Trabajo con repositorios remotos: push, pull y fetch
https://platzi.[com](https://)/home/clases/11059-gitgithub/71797-trabajo-con-repositorios-remotos-push-pull-y-fetch/

## Conceptos Clave Antes de Empezar
- Repositorio Local: Es el repositorio que tienes en tu computadora.
- Repositorio Remoto: Es el repositorio alojado en un servidor, como GitHub, GitLab, o Bitbucket.
- Remote (origin): Por defecto, cuando clonas un repositorio desde un servicio remoto, Git configura un remote llamado origin, que apunta al repositorio original.

## git push - Enviar Cambios al Repositorio Remoto
El comando git push se usa para enviar tus commits locales al repositorio remoto. Esto es útil cuando quieres compartir tus cambios con otros colaboradores o simplemente guardar una copia en la nube.

```bash
git push <remote> <branch>
    # <remote>: El nombre del repositorio remoto (por defecto, origin).
    # <branch>: El nombre de la rama que deseas subir (por ejemplo, main, develop, etc.).

git push origin main
# Este comando enviará todos los commits de tu rama main al repositorio remoto en GitHub (o el servicio que estés usando).

# Consideraciones
# Si es la primera vez que subes una nueva rama, es posible que necesites usar el flag -u para establecer el seguimiento:
git push -u origin nueva-rama
# Esto enlaza tu rama local con la rama remota, de modo que en futuras ocasiones solo necesitas ejecutar git push.
```

## git pull - Obtener y Fusionar Cambios desde el Repositorio Remoto
El comando git pull es una combinación de dos comandos: ```fetch``` (obtener los cambios) y ```merge``` (fusionar esos cambios). En esencia, git pull trae las actualizaciones desde el repositorio remoto y las fusiona con tu rama local.

```bash
git pull <remote> <branch>
    # <remote>: El nombre del repositorio remoto (por defecto, origin).
    # <branch>: La rama remota que deseas traer (por ejemplo, main, develop, etc.).

git pull origin main
# Esto traerá los últimos cambios de la rama main en el repositorio remoto y los fusionará con tu rama main local.
```
### Consideraciones
- Si hay conflictos entre los cambios remotos y tus cambios locales, Git te pedirá que los resuelvas manualmente.
- git pull es útil cuando trabajas en colaboración con otros, ya que asegura que siempre estés al día con los últimos cambios.

## git fetch - Obtener Cambios desde el Repositorio Remoto (Sin Fusionar)
A diferencia de git pull, el comando git fetch solo descarga los commits y ramas desde el repositorio remoto, pero no fusiona esos cambios con tu rama local. Esto te da la oportunidad de revisar los cambios antes de aplicarlos.
```bash
git fetch <remote>
    # <remote>: El nombre del repositorio remoto (por defecto, origin).

git fetch origin
# Este comando traerá todas las actualizaciones del repositorio remoto, incluidas las nuevas ramas y los commits, pero no afectará tu rama actual.

# Esto te mostrará los commits que están en el repositorio remoto pero que aún no están en tu rama local.
git log main..origin/main
# Se utiliza para mostrar los commits que están en origin/main pero que no están en tu rama local main.

git merge origin/main
# Después de git fetch, si quieres fusionar los cambios traídos
```