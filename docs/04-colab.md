# 4. Trabajar desde Google Colab

Colab ofrece dos formas diferentes de trabajar con GitHub. Guardar un notebook en GitHub no sube automáticamente los demás archivos del entorno.

## A. Interfaz gráfica: guardar un notebook

1. Entra en [Colab](https://colab.research.google.com/) con tu cuenta de Google.
2. Usa **File → Open notebook → GitHub** para buscar y abrir un notebook de un repositorio. Para usar el de este material antes de publicarlo, selecciona la pestaña **Upload** y carga `notebooks/practica_git.ipynb`.
3. Edita una celda de texto y añade lo que has aprendido.
4. Selecciona **File → Save a copy in GitHub**.
5. Autoriza el acceso a tu cuenta de GitHub si se solicita.
6. Elige tu repositorio, la rama `main`, una ruta como `notebooks/mi-practica.ipynb` y un mensaje de commit.
7. Confirma y comprueba el archivo y el commit en GitHub.

Esta operación publica el notebook seleccionado. No expone por separado los pasos add y push. Revisa las salidas del notebook antes de publicarlo; puedes omitirlas desde el diálogo si se ofrece esa opción.

## B. Consola dentro de las celdas

Abre el [notebook incluido](../notebooks/practica_git.ipynb) en Colab. Está preparado para clonar tu repositorio público, crear `notas-colab.md`, hacer add y commit y publicarlo con autenticación temporal.

Las diferencias frente a una terminal local son:

- `!git status` ejecuta un comando de sistema desde una celda.
- `%cd /content/mi-practica-git` cambia la carpeta para las celdas siguientes. `!cd` solo cambia la carpeta del proceso de esa ejecución.
- `!git --version` permite comprobar si Git está instalado. En el entorno habitual de Colab ya está disponible.
- Configura nombre y correo sin `--global`, dentro del clon, porque la sesión es temporal.
- Los archivos de `/content` y los commits que no hayas publicado pueden perderse al reiniciarse o eliminarse el entorno. Haz push y comprueba GitHub antes de salir.
- Guardar el notebook en Drive no guarda automáticamente el repositorio clonado en `/content`.

### Autenticación para push

El notebook solicita mediante `getpass` un token de acceso personal de alcance específico. Créalo en GitHub desde **Settings → Developer settings → Personal access tokens → Fine-grained tokens**. Selecciona como propietario tu cuenta, únicamente el repositorio de práctica, un vencimiento breve y **Repository permissions → Contents: Read and write**. Las organizaciones pueden requerir aprobación adicional.

El token se usa como contraseña HTTPS mediante un programa temporal de autenticación. No se incluye en la URL, el código guardado ni la salida. Aun así, utiliza solo un entorno personal de confianza, no compartas una sesión activa y revoca el token cuando termines.

El ejemplo clona un repositorio **público** sin autenticación. Si tu repositorio es privado, usa la ruta gráfica o adapta la autenticación temporal también para el clone; no pegues el token en `git clone`.

### Recuperar un error desde Colab

En la carpeta del clon, con el estado limpio y después de comprobar que HEAD es el commit erróneo:

```python
!git log --oneline -5
!git status
```

Fuentes: [ejemplo oficial de integración Colab–GitHub](https://github.com/googlecolab/colabtools/blob/main/notebooks/colab-github-demo.ipynb), [preguntas frecuentes de Colab](https://research.google.com/colaboratory/faq.html), [tokens de GitHub](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

[Inicio](../README.md) · [Recuperar versiones](05-recuperar-versiones.md)
