# 3. Trabajar desde la consola

Puedes ejecutar estos comandos en Git Bash, PowerShell, Terminal de macOS/Linux o **Terminal → New Terminal** en VS Code. Ejecuta un bloque cada vez y revisa el resultado. Sustituye `TU_USUARIO` por tu usuario real. Los comandos Git son los mismos en estos entornos.

## A. Empezar con un repositorio que ya existe en GitHub

Crea primero `mi-practica-git` en tu cuenta con README. Desde la carpeta donde quieras guardar tus proyectos:

```bash
git clone https://github.com/TU_USUARIO/mi-practica-git.git
cd mi-practica-git
git branch --show-current
git remote -v
git status
git pull --ff-only origin main
```

Debes estar en `main`, tener `origin` apuntando a tu cuenta y un estado sin cambios pendientes. Si tu rama tiene otro nombre, usa su nombre real en lugar de `main`.

## B. Crear, editar y añadir archivos

Abre esta carpeta en un editor. En VS Code puedes ejecutar `code .` si el comando está instalado; también puedes usar **File → Open Folder**.

Crea `mi-proyecto.md`, completa la ficha, copia una imagen a `images/mi-imagen.jpg` y enlázala. Guarda los archivos. Ahora revisa:

```bash
git status
git diff
git add mi-proyecto.md images/mi-imagen.jpg
git diff --staged
git commit -m "Añade la ficha y su imagen"
git push origin main
git status
```

`git diff` no muestra el contenido de archivos nuevos aún no seguidos. Ábrelos para revisarlos; después de add, `git diff --staged` muestra el contenido de texto que se confirmará. Las imágenes no tienen un diff textual útil.

Si tu imagen tiene otro nombre, usa su ruta real. `git add .` selecciona todos los cambios bajo la carpeta actual, incluidas eliminaciones; para aprender, selecciona archivos concretos.

## C. Actualizar

Antes de editar, si no hay cambios pendientes:

```bash
git pull --ff-only origin main
```

Modifica la descripción y guarda. Después:

```bash
git diff
git add mi-proyecto.md
git diff --staged
git commit -m "Actualiza la descripción del proyecto"
git push origin main
```

Aunque trabajes solo, la web, tu ordenador y Colab son copias distintas del mismo proyecto. Pull sirve para actualizarlas.

## D. Renombrar y eliminar

Crea `notas.md` desde tu editor y escribe dos ideas. Luego:

```bash
git add notas.md
git commit -m "Añade notas personales"
git push origin main
git mv notas.md ideas.md
git commit -m "Renombra las notas como ideas"
git push origin main
git rm ideas.md
git commit -m "Elimina el archivo de ideas"
git push origin main
```

`git mv` y `git rm` preparan sus cambios automáticamente. También puedes renombrar o eliminar desde el editor y ejecutar `git add -A` tras revisar el estado.

## E. Alternativa: empezar desde una carpeta local

Esta es otra ruta de inicio; no la ejecutes dentro del clon anterior. Crea en GitHub un repositorio **vacío**, sin README, licencia ni `.gitignore`, llamado `mi-practica-local`.

```bash
mkdir mi-practica-local
cd mi-practica-local
git init -b main
```

Crea `README.md` desde el editor y escribe un título. Después:

```bash
git add README.md
git commit -m "Crea el repositorio personal"
git remote add origin https://github.com/TU_USUARIO/mi-practica-local.git
git push -u origin main
```

`-u` vincula tu rama local con la remota: a partir de ahí puedes usar `git push` y `git pull --ff-only`. `git init` crea el repositorio local; no crea el repositorio en la web.

## F. Ver el historial

```bash
git log --oneline -10
git show HEAD
```

Pulsa `q` si el historial abre un visor. Cada hash identifica un commit. Sigue con [recuperar versiones](05-recuperar-versiones.md).

Fuentes: [manual de Git](https://git-scm.com/docs), [repositorios y remotos en VS Code](https://code.visualstudio.com/docs/sourcecontrol/repos-remotes).

[Inicio](../README.md) · [Colab](04-colab.md)
