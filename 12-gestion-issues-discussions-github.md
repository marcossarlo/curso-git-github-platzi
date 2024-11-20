> Introducción a GitHub:
# Gestión de Issues y Discussions en GitHub
https://platzi.com/home/clases/11059-gitgithub/71795-gestion-de-issues-y-discussions-en-github/

## ¿Qué son los Issues en GitHub?
Los Issues son una forma de rastrear tareas, mejoras, errores (bugs) o cualquier otra actividad relacionada con tu proyecto. Funcionan como un sistema de tickets que los equipos pueden usar para colaborar, priorizar y gestionar tareas.

## Casos de Uso Comunes de Issues
- Reportar errores (bugs).
- Solicitar nuevas funcionalidades.
- Discutir mejoras en el código.
- Documentar ideas o recopilar feedback.
- Asignar tareas a los colaboradores.

## Etiquetas (Labels) en Issues
Las etiquetas te ayudan a categorizar los Issues, facilitando la organización y búsqueda. GitHub incluye algunas etiquetas predeterminadas como bug, enhancement, help wanted, pero también puedes crear etiquetas personalizadas.

## Cómo Crear un Issue
Ve al repositorio en GitHub -> Haz clic en la pestaña "Issues" -> Selecciona "New issue" -> Llena los campos:

## Cierre Automático de Issues con Commits
Puedes cerrar automáticamente un Issue al hacer un commit, usando palabras clave en el mensaje del commit. Ejemplo:
```bash
git commit -m "Corrige el error de validación de formularios. Closes #42"
# Esto cerrará el Issue número #42 cuando el commit sea empujado al repositorio remoto.
```

## ¿Qué es un Issue Template?
Un Issue Template es un archivo predefinido que proporciona un formulario o guía cuando alguien crea un nuevo issue en tu repositorio. Estos templates pueden incluir:
- Campos prellenados para la descripción.
- Instrucciones específicas para los usuarios.
- Secciones para detalles como pasos para reproducir un error, capturas de pantalla, etc.

### Cómo Crear un Issue Template en GitHub
#### Paso 1: Crear un Directorio .github/ISSUE_TEMPLATE
- Crea una nueva carpeta llamada .github si no existe.
- Dentro de la carpeta .github, crea otra llamada ISSUE_TEMPLATE.
```
.github/
└── ISSUE_TEMPLATE/
```
#### Paso 2: Crear un Archivo de Template
Dentro de la carpeta ISSUE_TEMPLATE, puedes crear un archivo para cada tipo de issue que desees:
- ```bug_report.md``` para reportar errores.
- ```feature_request.md``` para solicitar nuevas funcionalidades.
- ```custom_template.md``` para otras necesidades.

#### Paso 3: Escribir el Contenido del Template
```markdown
---
name: 🐞 Reportar un Bug
about: Reportar un error para ayudarnos a mejorar
title: "[BUG] Título descriptivo"
labels: bug
assignees: ''

---

**Descripción del error**
Una descripción clara y concisa del error.

**Pasos para reproducir**
1. Ir a '...'
2. Hacer clic en '...'
3. Desplazarse hacia abajo hasta '...'
4. Ver el error

**Comportamiento esperado**
Una descripción clara y concisa de lo que esperabas que sucediera.

**Capturas de pantalla**
Si es posible, añade capturas de pantalla para ayudar a explicar tu problema.

**Información adicional**
Cualquier otra cosa que creas que pueda ser relevante.
```

#### Paso 4: Subir los Templates al Repositorio
Una vez que hayas creado el archivo, confirma y sube los cambios:
```
git add .github/ISSUE_TEMPLATE/bug_report.md
git commit -m "Agregar template para reportar bugs"
git push origin main
```

## GitHub Discussions: Fomentar la Colaboración y la Comunidad
Las Discussions son una herramienta para fomentar la colaboración abierta y la discusión en torno a un proyecto. A diferencia de los Issues, que están orientados a tareas específicas, las Discussions están diseñadas para charlas generales, ideas, preguntas y debates.

### Casos de Uso Comunes de Discussions
- Preguntas y respuestas: Un lugar para que los usuarios hagan preguntas sobre el uso del proyecto.
- Sugerencias y brainstorming: Discutir nuevas ideas o enfoques.
- Anuncios: Compartir actualizaciones importantes o nuevos lanzamientos.
- Comunicación con la comunidad: Fomentar un espacio para que los usuarios y colaboradores se conecten.

### Características Clave de Discussions
- Respuestas marcadas: Permite marcar una respuesta como la "respuesta correcta" para preguntas.
- Votación: Los usuarios pueden votar (👍 o 👎) en publicaciones y respuestas, lo que ayuda a destacar las mejores respuestas.
- Categorías personalizadas: Los propietarios del repositorio pueden crear categorías personalizadas para organizar mejor las Discussions.

### Habilitar GitHub Discussions en tu Repositorio
Si no aparece la opci´pn Dicussions hay que habilitarla:
- Ve a tu repositorio en GitHub.
- Haz clic en la pestaña "Settings" (Configuración). Esta pestaña está disponible solo para los administradores del repositorio.
- Desplázate hacia abajo hasta la sección "Features".
- Busca la opción "Discussions".
- Marca la casilla "Enable discussions" (Habilitar discusiones).
