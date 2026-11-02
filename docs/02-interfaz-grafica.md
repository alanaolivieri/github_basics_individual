# 2. Trabajar desde la interfaz gráfica

Usaremos `mi-practica-git`, creado en tu cuenta según las [instrucciones](../instrucciones.md). Los nombres de los menús pueden aparecer traducidos.

## A. GitHub en el navegador

### Crear un archivo

1. Entra en tu repositorio y comprueba que la rama seleccionada es `main`.
2. Pulsa **Add file → Create new file**.
3. Escribe `mi-proyecto.md` y copia la [plantilla](../mi-proyecto.md).
4. Pulsa **Preview** para revisar el Markdown.
5. Pulsa **Commit changes**, escribe `Crea la ficha personal`, elige confirmar directamente en `main` y confirma.

En la web no ejecutas add ni push por separado: la confirmación registra el archivo directamente en GitHub.

### Actualizar y añadir una imagen

1. Abre `mi-proyecto.md` y pulsa el lápiz para editarlo.
2. Completa la ficha, revisa la vista previa y confirma con `Completa la ficha personal`.
3. Vuelve a la lista de archivos y pulsa **Add file → Upload files**. Arrastra una carpeta `images` que contenga tu imagen; alternativamente entra primero en `images` y carga allí el archivo. Confirma la carga.
4. Edita la ficha y añade `![Mi imagen](images/mi-imagen.jpg)`, adaptando el nombre y la extensión.
5. Confirma y comprueba que la imagen se ve.

GitHub distingue mayúsculas y minúsculas en las rutas: `Foto.JPG` y `foto.jpg` no son intercambiables.

### Renombrar y eliminar

- **Renombrar:** abre el archivo, pulsa editar, cambia su nombre en el campo de ruta y confirma.
- **Eliminar:** abre el archivo y busca **Delete file** en el menú de acciones `…`; confirma la eliminación con un mensaje claro.

Ambas operaciones quedan en el historial y se pueden recuperar.

### Consultar el historial

En un archivo, abre **History**. En la página principal del repositorio, abre el enlace de commits junto al último cambio. Selecciona un commit para ver las diferencias. Para recuperar versiones, consulta la [guía 5](05-recuperar-versiones.md).

## B. GitHub Desktop: flujo local sin comandos

### Clonar y abrir

1. Inicia sesión en Desktop.
2. **File → Clone repository → URL**.
3. Pega la URL HTTPS de tu repositorio, elige una carpeta local y pulsa **Clone**.
4. Comprueba que **Current branch** muestra `main`.
5. Pulsa **Fetch origin** y, si aparece, **Pull origin** antes de editar.
6. Usa **Repository → Open in Visual Studio Code**, o abre la carpeta con tu editor.

Clonar conserva el historial y la conexión remota. **Download ZIP** solo descarga archivos: no equivale a clonar.

### Editar, seleccionar, confirmar y publicar

1. Modifica y guarda `mi-proyecto.md` desde el editor.
2. Copia una imagen a `images` desde el explorador de archivos y añade su enlace a la ficha.
3. Vuelve a Desktop: los cambios aparecen en **Changes**.
4. Revisa las diferencias y marca los archivos que quieres incluir en el commit. Esta selección cumple el papel de escoger cambios para confirmar; no necesitas ejecutar `git add`.
5. En **Summary**, escribe un mensaje y pulsa **Commit to main**.
6. Pulsa **Push origin**.
7. Abre GitHub y verifica que aparecen tus cambios.

Para renombrar o eliminar, hazlo desde el explorador o editor, guarda y repite el ciclo de revisión, commit y push. Si editaste en la web, usa **Fetch origin → Pull origin** antes de continuar localmente.

## C. VS Code: controles gráficos de Git

Git debe estar instalado por separado y configurado según la [preparación](01-preparacion.md).

1. Abre la paleta con `Ctrl+Shift+P` en Windows/Linux o `Cmd+Shift+P` en macOS.
2. Ejecuta **Git: Clone**, pega la URL y elige una carpeta. Abre el repositorio clonado.
3. Edita y guarda un archivo desde el explorador de VS Code.
4. Abre **Source Control / Control de código fuente**.
5. Selecciona un archivo para revisar sus diferencias.
6. Pulsa **+** junto al archivo para **Stage Changes**: equivale a seleccionar ese contenido con add.
7. Escribe un mensaje y pulsa **Commit**.
8. En el menú `…`, utiliza **Push**. Si te pide autenticación, completa el acceso con GitHub.
9. Comprueba el resultado en GitHub.

El botón **Sync Changes** puede traer cambios y después subir los tuyos. Para aprender cada operación por separado, usa **Pull** y **Push** desde el menú. Puedes consultar **Source Control Graph** para el historial.

Fuentes: [archivos en GitHub](https://docs.github.com/en/repositories/working-with-files), [GitHub Desktop](https://docs.github.com/en/desktop), [operaciones de staging en VS Code](https://code.visualstudio.com/docs/sourcecontrol/staging-commits).

[Inicio](../README.md) · [Consola](03-consola.md)
