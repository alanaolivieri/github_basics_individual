# 5. Volver a una versión anterior

Antes de continuar, guarda tu trabajo, confirma los cambios que quieras conservar y comprueba que no quedan cambios pendientes. En consola usa `git status`; en Desktop revisa **Changes**.

## Elige qué quieres recuperar

| Objetivo | Interfaz gráfica | Consola |
|---|---|---|
| Ver cómo era un archivo | GitHub → archivo → History → commit | `git show HASH:mi-proyecto.md` |
| Recuperar una versión de un archivo | Copiar su contenido antiguo y confirmarlo como nueva edición | `git restore --source=HASH -- mi-proyecto.md`, add y commit |
| Deshacer un commit publicado | Desktop → History → Revert Changes in Commit | `git revert --no-edit HASH`, después push |
| Deshacer el último commit aún local conservando las ediciones | VS Code → Undo Last Commit | `git reset --soft HEAD~1` |

Sustituye `HASH` por el identificador real del commit; no escribas literalmente `HASH`. `HEAD` es el commit actual y `HEAD~1` su padre.

## A. Deshacer un error publicado: práctica recomendada

Supón que tu historial lineal es `A → B → C`, y C solo cambia el título correcto por uno incorrecto. Revertir C genera D, que deshace ese cambio: `A → B → C → D`. C permanece en el historial.

### Con GitHub Desktop

1. Abre tu clon y comprueba `main`.
2. Pulsa **Fetch origin** y después **Pull origin** si aparece.
3. En **History**, selecciona el commit que introdujo el error, no el commit al que quieres parecerte.
4. Haz clic derecho y selecciona **Revert Changes in Commit**.
5. Revisa la ficha: debe volver el título correcto.
6. Pulsa **Push origin** y comprueba el nuevo commit en GitHub.

Para deshacer varios commits, reviértelos del más reciente al más antiguo y revisa el resultado después de cada uno.

### Con consola o terminal de VS Code

```bash
git status
git pull --ff-only origin main
git log --oneline -5
```

Si el último commit es exactamente el error del ejercicio:

```bash
git revert --no-edit HEAD
git push origin main
```

Para otro commit, usa su hash en lugar de HEAD. Revert deshace los cambios de ese commit; no garantiza que todo el proyecto quede igual que una instantánea antigua si hubo más cambios después.

Si hay conflictos, puedes cancelar con `git revert --abort`. Para continuar, edita los archivos afectados, elimina los marcadores de conflicto, conserva el contenido correcto, ejecuta `git add` sobre esos archivos y después `git revert --continue`. No hagas push hasta revisar el resultado. Esta práctica usa commits normales, no commits de merge.

## B. Recuperar solo una versión anterior de un archivo

### Desde GitHub web

1. Abre `mi-proyecto.md` y su **History**.
2. Selecciona el commit que contiene la versión deseada y abre el archivo en esa revisión; puedes usar **Browse files** para localizarlo.
3. Copia el contenido de esa versión, por ejemplo desde **Raw**.
4. Vuelve a `main`, abre el archivo actual y pulsa editar.
5. Sustituye el contenido por el antiguo y confirma con `Recupera la versión anterior de la ficha`.

Esto crea un nuevo commit en `main`. No edites creyendo que estás en `main` mientras navegas por un hash antiguo. Si el archivo fue eliminado, créalo otra vez con la misma ruta y el contenido recuperado.

### Desde consola

Localiza el commit deseado:

```bash
git log --oneline -- mi-proyecto.md
git show HASH:mi-proyecto.md
```

Cuando hayas identificado el correcto:

```bash
git restore --source=HASH -- mi-proyecto.md
git diff
git add mi-proyecto.md
git commit -m "Recupera la versión anterior de la ficha"
git push origin main
```

Restore sustituye el contenido de trabajo de ese archivo. Hazlo con el estado limpio para no sobreescribir ediciones que aún necesitas.

## C. Consultar todo el proyecto antiguo sin cambiar main

Con el estado limpio:

```bash
git switch --detach HASH
```

Puedes inspeccionar los archivos de esa versión. Estás en un estado separado de las ramas. Para volver:

```bash
git switch main
```

Si quieres trabajar a partir de ese punto, crea una rama antes de editar: `git switch -c exploracion-antigua`.

## D. Deshacer el último commit que todavía no has subido

Úsalo solo si existe un commit anterior y el commit que quitas no se ha publicado.

- **VS Code:** en Source Control, abre `… → Commit → Undo Last Commit`. Las ediciones se conservan para corregirlas y confirmarlas otra vez.
- **Consola:** ejecuta `git reset --soft HEAD~1`. El commit sale de la rama local y sus cambios quedan preparados para un nuevo commit.

Revisa, corrige y confirma otra vez. No uses este procedimiento para un commit ya publicado. `reset --hard` puede borrar cambios de trabajo y no es necesario para esta práctica. Revert permite corregir sin forzar el push.

Fuentes: [revert en Desktop](https://docs.github.com/en/desktop/managing-commits/reverting-a-commit-in-github-desktop), [git revert](https://git-scm.com/docs/git-revert), [git restore](https://git-scm.com/docs/git-restore), [deshacer en VS Code](https://code.visualstudio.com/docs/sourcecontrol/staging-commits).

[Inicio](../README.md) · [Chuleta](06-chuleta.md)
