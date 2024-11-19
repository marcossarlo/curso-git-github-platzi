> Introducción a GitHub:
# Cómo configurar Key PAT & SSH para GitHub: Guía paso a paso
[https://platzi.com/home/clases/11059-gitgithub/71823-configuracion-de-llaves-ssh/
](https://)

GitHub dejó de soportar la autenticación con usuario y contraseña. Ahora debes usar tokens de acceso personal (PAT) o autenticación SSH.

Los Tokens de Acceso Personal funcionan como contraseñas, pero son mucho más seguras. Desde agosto de 2021, GitHub eliminó el soporte para la autenticación mediante contraseña, obligando a los usuarios a utilizar PAT en su lugar.

## Usar un Token de Acceso Personal (PAT)
Para autenticar operaciones de Git vía HTTPS.
### Pasos para generar y usar un token de acceso personal:
```bash
1. Generar el token de acceso personal (PAT):
- Ve a GitHub y accede a tu cuenta.
- Ve a **Settings** (Configuración) → **Developer Settings** → **Personal Access Tokens**.
- Haz clic en **Generate new token**.
- Asigna un nombre al token y selecciona los permisos adecuados (como `repo` para acceso completo a tus repositorios).
- Haz clic en **Generate token**.

Guarda el token en un lugar seguro, ya que no podrás verlo de nuevo.

2. Clonar un Repositorio con HTTPS:
git clone https://github.com/usuario/repositorio.git

3. Usar el token en Git:
- Cuando intentes hacer `git push`, Git te pedirá tu **usuario** y luego la **contraseña**.
- En lugar de ingresar tu contraseña, **usa el token generado** como la "contraseña".
```

## Autenticación SSH
La Autenticación SSH utiliza pares de claves (una clave privada en tu máquina local y una clave pública que subes a GitHub). Es considerada la opción más segura porque elimina la necesidad de ingresar contraseñas o tokens.

### Cómo Usar SSH:
```bash
1. Generar una Clave SSH:
ssh-keygen -t ed25519 -C "tu-email@example.com"
 -t ed25519 establece el nivel de encriptación.
 -C añade un comentario con tu correo, útil para identificar la llave en GitHub.
(Puedes usar rsa en lugar de ed25519 si necesitas compatibilidad más amplia).

2. Guardar y proteger la llave:
Usa el nombre por defecto y añade una passphrase segura.
La llave pública se guarda en el directorio .ssh, generalmente nombrada id_ed25519.pub.

3. Añadir la Clave SSH a tu Agente SSH:
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

3. Agregar la Clave Pública a GitHub:
# Copia la clave pública
cat ~/.ssh/id_ed25519.pub
Ve a tu perfil de GitHub → Settings → SSH and GPG keys → New SSH key y pega la clave.

4. Comprobar autenticación: En la terminal, ejecuta el comando:
ssh -T git@github.com

5. Clonar un Repositorio con SSH:
git clone git@github.com:usuario/repositorio.git
```

## ¿Cuál Método Recomiendo?
- Para la mejor seguridad y conveniencia a largo plazo: Usa Autenticación SSH.
    - No tienes que preocuparte por la caducidad del token.
    - Es extremadamente seguro siempre que protejas tu clave privada.
    - No necesitas ingresar credenciales cada vez que interactúas con GitHub.
- Para una configuración rápida y temporal: Usa Tokens de Acceso Personal (PAT).
    - Ideal si necesitas acceso rápido y no quieres configurar claves SSH.
    - Útil para integraciones automáticas o configuraciones en servidores donde no puedes usar SSH.
