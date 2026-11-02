# 6. Chuleta y problemas frecuentes

## Equivalencias

| Acción | GitHub web | GitHub Desktop | VS Code | Consola |
|---|---|---|---|---|
| Crear remoto | New repository | Crear local y Publish repository | Publish to GitHub | Crear en web o usar GitHub CLI |
| Clonar | Copiar URL en Code | File → Clone repository | Git: Clone | `git clone URL` |
| Revisar cambios | Preview / vista de diferencias | Changes | Source Control | `git status`, `git diff` |
| Seleccionar | Se confirma la edición web | Casillas de Changes | + / Stage Changes | `git add archivo` |
| Confirmar | Commit changes, ya en remoto | Commit to main, local | Commit, local | `git commit -m "Mensaje"` |
| Subir | Incluido en la confirmación web | Push origin | Push | `git push origin main` |
| Actualizar local | Recargar muestra el remoto | Fetch y Pull origin | Pull | `git pull --ff-only origin main` |
| Deshacer publicado | Recuperar contenido antiguo como nueva edición | Revert Changes in Commit | Terminal integrada | `git revert --no-edit HASH` y push |

## Ciclo habitual

```bash
git status
git pull --ff-only origin main
# Edita y guarda desde tu editor
git diff
git add mi-proyecto.md
git diff --staged
git commit -m "Describe el cambio"
git push origin main
git log --oneline -5
```

Ejecuta pull con el estado limpio. Revisa cada resultado antes de avanzar.

## Soluciones habituales

| Mensaje o síntoma | Qué revisar |
|---|---|
| `git` no se reconoce | Instala Git y vuelve a abrir terminal y VS Code. |
| `gh` no se reconoce | GitHub CLI es una instalación distinta; puedes usar Desktop o el gestor de credenciales. |
| `not a git repository` | Entra con `cd` en la carpeta clonada que contiene `.git`. |
| `Author identity unknown` | Configura `user.name` y `user.email`. |
| `nothing to commit` | Guarda el archivo, comprueba la carpeta y revisa `git status`. Quizá ya confirmaste el cambio. |
| `src refspec main does not match any` | Comprueba el nombre de rama y que exista al menos un commit. |
| `remote origin already exists` | Consulta `git remote -v`. Si la URL es incorrecta, usa `git remote set-url origin URL_CORRECTA`. |
| `Authentication failed` / `403` | Comprueba la cuenta autenticada, acceso de escritura y permisos del token. El nombre y correo de Git no autentican. |
| Push rechazado por cambios remotos | No fuerces el push. Con el estado limpio, ejecuta `git pull --ff-only origin main`. |
| Pull indica que no puede avanzar en fast-forward | Las historias han divergido. Con el estado limpio, usa `git fetch origin`, revisa `git log --oneline --graph --all -15` y ejecuta `git merge origin/main` para integrar. |
| Conflicto durante merge | Abre los archivos, conserva el contenido correcto y elimina los marcadores. Guarda, haz add y commit, revisa y después push. Para cancelar un merge en curso: `git merge --abort`. |
| La imagen no aparece | Comprueba ruta relativa, extensión, mayúsculas y que hayas subido la imagen. |
| No veo el cambio en GitHub | Comprueba si hiciste commit pero olvidaste push, y si estás mirando el repositorio y la rama correctos. |
| Colab ha perdido la carpeta | El entorno es temporal. Clona de nuevo y recupera lo que llegaste a publicar. |

Un repositorio público es visible para cualquiera. No publiques contraseñas, tokens ni datos personales ajenos. Añadir un archivo a `.gitignore` no elimina versiones ya publicadas; si has expuesto un token, revócalo.

[Inicio](../README.md)
