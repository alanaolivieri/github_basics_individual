# Cómo subir un repositorio a tu GitHub

## Con GitHub Desktop

1. Abre Desktop y usa **File → Add local repository** para seleccionar esta carpeta.
2. Si no contiene un repositorio Git, usa el enlace **create a repository here**. Verifica que la ruta final sea esta misma carpeta y no una subcarpeta duplicada.
3. Revisa todos los archivos, crea el primer commit si aún no existe y pulsa **Publish repository**.
4. Usa como nombre `github_basics_individual` y elige la visibilidad. Para compartirlo con la comunidad, desmarca **Keep this code private**.
5. Abre el repositorio en GitHub y comprueba que el README y sus enlaces funcionan.

## Con consola

- Si has creado la carpeta en Local:
Crea en GitHub un repositorio vacío `github_basics_individual`, sin README ni licencia ni `.gitignore`. Abre la terminal en esta carpeta y ejecuta, sustituyendo `TU_USUARIO`:

```bash
git init -b main
git add .
git diff --staged --stat
git commit -m "Añade la práctica individual de Git y GitHub"
git remote add origin https://github.com/TU_USUARIO/github_basics_individual.git
git push -u origin main
```

- Si ya inicializaste la carpeta desde Desktop, utiliza ese repositorio existente en lugar de repetir la inicialización y el alta del remoto.

## Con el navegador

Crea el repositorio y usa **Add file → Upload files**. Arrastra el contenido de esta carpeta, conservando `docs/`, `images/` y `notebooks/`. Comprueba que `README.md` queda en la raíz, no dentro de otra carpeta `github_basics_individual`. El navegador puede omitir archivos ocultos: revisa `.gitignore` o créalo mediante **Add file → Create new file**.

