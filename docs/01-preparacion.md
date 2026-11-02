# 1. Preparar Git y tu cuenta

## Qué necesitas según tu ruta

| Ruta | Necesitas |
|---|---|
| GitHub en el navegador | Cuenta de GitHub y navegador. No requiere instalar Git. |
| GitHub Desktop | Cuenta y GitHub Desktop, que incluye su propio Git. |
| VS Code o terminal local | Git instalado, cuenta y autenticación con GitHub. |
| Google Colab | Cuenta de Google, cuenta de GitHub y un notebook. El entorno es temporal. |

## Instalar Git

Descarga Git desde [git-scm.com](https://git-scm.com/downloads) y sigue las instrucciones de tu sistema:

- **Windows:** ejecuta el instalador. Puedes mantener las opciones predeterminadas, incluyendo el gestor de credenciales. Después abre Git Bash, PowerShell o la terminal de VS Code.
- **macOS:** sigue las opciones oficiales de descarga; `git --version` también puede ofrecer instalar las herramientas de línea de comandos de Apple.
- **Linux:** usa el gestor de paquetes de tu distribución. En Ubuntu/Debian: `sudo apt update` y después `sudo apt install git`.

Cierra y vuelve a abrir la terminal tras instalarlo. Comprueba:

```bash
git --version
```

Si aparece una versión, está disponible en esa terminal. Para VS Code instala también [Visual Studio Code](https://code.visualstudio.com/).

## Configurar quién firma tus commits

Sustituye los datos de ejemplo por los tuyos:

```bash
git config --global user.name "Tu nombre"
git config --global user.email "tu-correo-asociado-a-github@example.com"
git config --global init.defaultBranch main
git config --global --get user.name
git config --global --get user.email
```

El nombre puede ser tu nombre real: no tiene que coincidir con tu usuario. Usa un correo verificado de tu cuenta o copia exactamente el correo privado `noreply` que muestra GitHub en **Settings → Emails**. No inventes esa dirección.

`--global` aplica a tu usuario de ese ordenador. Para una identidad específica, ejecuta los mismos comandos dentro del repositorio sin `--global`.

**Configurar nombre y correo identifica al autor; no inicia sesión ni concede permiso para subir archivos.**

## Autenticarte con GitHub

Para empezar, utiliza HTTPS. Elige uno de estos métodos:

### GitHub Desktop

Instala [GitHub Desktop](https://desktop.github.com/) y abre **File → Options → Accounts → Sign in** en Windows, o **GitHub Desktop → Settings → Accounts** en macOS. Completa el inicio de sesión en el navegador. En los ajustes de Git, verifica también tu nombre y correo.

### VS Code

Al clonar un repositorio privado o publicar cambios, completa el inicio de sesión con GitHub cuando VS Code lo solicite y autoriza la conexión en el navegador. Tener iniciada una sesión para otra extensión no garantiza que Git ya esté autenticado.

### Terminal

Puedes usar el gestor de credenciales de Git, que abrirá el navegador cuando corresponda. Otra opción explícita es instalar [GitHub CLI](https://cli.github.com/) y ejecutar:

```bash
gh auth login
gh auth setup-git
gh auth status
```

En el asistente elige GitHub.com, HTTPS y acceso con navegador. `gh` se instala por separado: no es el comando `git`.

GitHub no acepta la contraseña de tu cuenta como contraseña de Git por HTTPS. Si utilizas un token, debe tener acceso al repositorio y permisos mínimos para la operación. No lo escribas dentro de la URL del repositorio, archivos, capturas ni notebooks. SSH es una alternativa, pero no es necesario para esta práctica.

## Comprobar la conexión

Clonar un repositorio público no prueba que puedas hacer push. La comprobación completa llegará al subir tu primer commit a **tu propio repositorio**.

Fuentes: [configurar Git](https://docs.github.com/en/get-started/git-basics/set-up-git), [autenticación con GitHub CLI](https://cli.github.com/manual/gh_auth_login).

[Inicio](../README.md) · [Siguiente: interfaz gráfica](02-interfaz-grafica.md)
