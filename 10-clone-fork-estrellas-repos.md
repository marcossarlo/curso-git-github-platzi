> Introducción a GitHub:
# Clone, fork y estrellas a repositorios
[https://platzi.com/home/clases/11059-gitgithub/71796-clone-fork-y-estrellas-a-repositorios/](https://)

## Clonar (Clone)
Clonar un repositorio significa crear una copia exacta del repositorio en tu máquina local. El repositorio que clones sigue apuntando al repositorio original (conocido como remoto).

```
git clone https://github.com/usuario/repositorio.git
```
### Cuándo Usar git clone:
- Acceso de solo lectura: Si solo quieres explorar el código, probarlo o hacer cambios locales sin intención de contribuir de vuelta al repositorio original.
- Colaborar en un equipo cerrado: Si eres miembro de un equipo trabajando en un repositorio privado donde todos tienen acceso de escritura.
- Proyectos personales: Si solo estás haciendo una copia para uso personal o para experimentar.

### Consideraciones al Clonar:
- Permisos: Sigues apuntando al repositorio original. Si no tienes permisos de escritura, no podrás hacer push de tus cambios al repositorio original.
- Ramas: Todas las ramas del repositorio original estarán disponibles en tu copia local.
- Contribuir de vuelta: Si deseas enviar tus cambios al repositorio original pero no tienes permisos, puedes hacerlo mediante un Pull Request solo si el repositorio es público o tienes acceso adecuado.

## Hacer un Fork (Fork)
Forkear un repositorio significa crear una copia completa del repositorio en tu cuenta de GitHub. Esto crea un nuevo repositorio bajo tu propio perfil, pero con el historial completo del original.

### Cuándo Usar Fork:
- Contribuir a proyectos Open Source: Si quieres hacer cambios en un repositorio al que no tienes acceso de escritura. Podrás enviar tus cambios al proyecto original mediante un Pull Request.
- Desarrollar características independientes: Si deseas trabajar en una característica específica sin afectar el repositorio original.
- Personalizar un proyecto: Si deseas mantener tu propia versión del proyecto con modificaciones que no necesariamente se integrarán en el proyecto original.

### Consideraciones al Hacer Fork:
- Repositorio independiente: Tu fork es independiente del repositorio original. Puedes modificarlo sin afectar el original.
- Mantener sincronizado: Debes asegurarte de mantener tu fork actualizado con el repositorio original, especialmente si este se actualiza con frecuencia.
```bash
git remote add upstream https://github.com/original-usuario/repositorio.git
git fetch upstream
git merge upstream/main
```
- Pull Requests: Si haces un cambio que crees que beneficiará al proyecto original, puedes enviar un Pull Request desde tu fork.

## Ejemplo Práctico: Forkear un proyecto open source, modificar y contribuir:
```bash
# Fork en GitHub.

# Clonar tu fork localmente:
git clone https://github.com/marcossarlo/mi-fork-proyecto.git

# Crear una rama nueva para tu cambio
git checkout -b feature-nueva

# Hacer tus cambios, commit y push:
git add .
git commit -m "Añadida nueva funcionalidad"
git push origin feature-nueva

# Enviar un Pull Request desde tu fork al repositorio original.
```
## Cómo Mantener tu Fork Actualizado
Cuando haces un fork de un repositorio en GitHub, estás creando una copia del repositorio original (upstream) bajo tu cuenta. A partir de ese momento, tu fork se convierte en un repositorio independiente. Esto significa que, si el repositorio original recibe nuevas actualizaciones (commits, pull requests aceptadas, etc.), tu fork no se actualiza automáticamente. Por lo tanto, es importante que lo mantengas sincronizado para estar al día con los cambios del proyecto original.

```bash
# Añadir el repositorio original como 'upstream'
git remote add upstream https://github.com/original-usuario/repositorio.git

# Verificar que 'upstream' se haya añadido correctamente
git remote -v

# Obtener las Últimas Actualizaciones del Repositorio Original
git fetch upstream

# Fusionar los Cambios en tu Rama Principal (main)
git checkout main
git merge upstream/main

# Subir los Cambios a tu Fork en GitHub
git push origin main
```
### Resumen del Flujo de Trabajo
1. Haz fork del repositorio original en GitHub.
2. Clona tu fork a tu máquina local.
3. Configura el remoto upstream para el repositorio original.
4. Trabaja en tus propias ramas (feature/mi-cambio).
5. Mantén tu rama main sincronizada con el upstream.
6. Si quieres enviar tus cambios al proyecto original, crea un Pull Request desde tu fork.

## git remote 
El comando git remote es una herramienta poderosa en Git que te permite gestionar las conexiones remotas a otros repositorios. Estas conexiones remotas son esencialmente enlaces a repositorios alojados en servicios como GitHub, GitLab, Bitbucket, o incluso en otros servidores.

Por defecto, cuando clonas un repositorio, Git crea un remote llamado origin, que apunta al repositorio del cual se clonó.

## Recomendaciones Generales
- Usa git clone si tienes acceso completo al repositorio y quieres colaborar directamente.
- Usa fork si deseas contribuir a un proyecto donde no tienes permisos de escritura o si planeas desarrollar una versión personalizada de ese proyecto.
- Mantén tus ramas organizadas y asegúrate de crear Pull Requests claros y detallados cuando contribuyas a otros proyectos.

## ¿Qué beneficios aporta usar estrellas en GitHub?
Las estrellas en GitHub funcionan como un sistema de marcado para resaltar los repositorios que deseas tener a mano como referencia o favoritos. Son útiles para:
- Crear un índice de repositorios de referencia o inspiración.
- Acceder rápidamente a recursos clave desde tu perfil.
- Seguir el desarrollo de proyectos importantes para tus intereses.