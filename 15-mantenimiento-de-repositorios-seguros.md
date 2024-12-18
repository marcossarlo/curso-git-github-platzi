# Mantenimiento de repositorios seguros
https://platzi.com/home/clases/11059-gitgithub/71806-mantenimiento-de-repositorios-seguros/

## 2 mejores prácticas al trabajar con repositorios
1. Tipo repositorio
    Repositorio Privado y Públicos
2. Uso de .gitignore 

##  Uso de .gitignore
El archivo .gitignore es esencial para evitar que ciertos archivos o carpetas sean rastreados por Git. Esto ayuda a mantener tu repositorio limpio y seguro al no incluir datos sensibles o archivos innecesarios.

### ¿Qué incluir en .gitignore?
- Archivos de configuración local:
  - Credenciales o configuraciones específicas de tu entorno.
  - Ejemplo: .env, settings.json.
- Datos sensibles:
  - Claves API, contraseñas, o tokens de acceso.
  - Nunca subas este tipo de datos a GitHub.
- Dependencias y librerías:
  - Ejemplo: node_modules/, vendor/.
  - Estas carpetas son voluminosas y se pueden reinstalar usando herramientas como npm o Composer.
- Archivos generados automáticamente:
  - Archivos de compilación, binarios o logs.
  - Ejemplo: *.log, *.exe, dist/.
- Sistemas Operativos y editores:
  - Ejemplo: *.DS_Store, .vscode/, Thumbs.db.

