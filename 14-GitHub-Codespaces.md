> GitHub Codespaces
# Cómo usar GitHub Codespaces: Configuración y Desarrollo en la Nube
https://platzi.com/home/clases/11059-gitgithub/71802-introduccion-a-github-codespaces/

GitHub Codespaces es una herramienta poderosa que permite crear y gestionar entornos de desarrollo en la nube, aumentando la flexibilidad y productividad para desarrolladores en cualquier lugar. Con una interfaz similar a **Visual Studio Code**, Codespaces permite desarrollar proyectos desde cualquier dispositivo, sin importar si está instalado el entorno completo en la máquina local.

## ¿Qué es GitHub Codespaces y cómo funciona?
GitHub Codespaces ofrece entornos de desarrollo alojados en máquinas virtuales en la nube. Esto permite a los desarrolladores trabajar desde cualquier dispositivo, como una tableta o teléfono, en proyectos alojados en repositorios de GitHub. Con acceso a herramientas de compilación y despliegue, se puede trabajar con múltiples lenguajes de programación sin necesidad de instalarlos localmente.

## ¿Cómo se crea un Codespace?
- Selecciona “New Codespace” en el menú.
- Escoge el repositorio en el que vas a trabajar.
- Elige la rama y región que prefieras.
- Configura el tipo de máquina virtual, seleccionando entre diferentes núcleos y memoria RAM según la necesidad del proyecto.

Una vez creado, se abre una interfaz de desarrollo completa, que incluye explorador de archivos, terminal integrada y control de versiones.

## ¿Cuáles son las características clave de Codespaces?
Algunas funcionalidades destacadas incluyen:
- Explorador de archivos y extensiones: permite administrar archivos y añadir extensiones, igual que en VS Code.
- Terminal integrada: facilita ejecutar comandos sin salir del entorno.
- Preconfiguración de entornos: lenguajes como Node, Python y .NET ya están instalados, permitiendo trabajar sin configurarlos en la máquina local.

## ¿Cómo se gestiona un proyecto en Codespaces?
Puedes crear y gestionar proyectos en múltiples lenguajes. Por ejemplo, para un proyecto en .NET:
- Crea una carpeta para el proyecto en la rama del repositorio.
- Usa comandos como .NET new console para iniciar el proyecto, sin preocuparte por tener .NET instalado localmente.
- La terminal permite ejecutar el proyecto con .NET run y hacer ajustes sobre la marcha.

## ¿Cómo hacer commit y sincronizar cambios?
Al realizar cambios en el proyecto, estos se pueden ver en la sección de control de versiones:
1. Añade un mensaje de commit que describa los cambios.
2. Sincroniza los cambios para reflejarlos en el repositorio de GitHub.

Esta integración asegura que cada modificación quede guardada y reflejada en GitHub, como si se hubiese hecho en un entorno local.

## ¿Por qué es importante eliminar Codespaces al terminar?
Cada Codespace utiliza recursos de GitHub y, en cuentas gratuitas, existe un límite de 120 horas de uso al mes. Al completar una tarea:
- Elimina el Codespace para evitar cargos adicionales.
- Desde “My Codespaces”, selecciona el Codespace y elige “delete” para confirmar la eliminación.

Este proceso garantiza que solo uses el tiempo necesario y no excedas el límite de la cuenta gratuita.