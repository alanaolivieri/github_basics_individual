# Tu práctica individual

## Objetivo

Aprender a gestionar versiones de tus archivos sin depender de otras personas. El contenido puede ser sencillo: cine, naturaleza, deporte, tecnología, arte o viajes.

## 1. Crea tu repositorio

En GitHub, inicia sesión y pulsa **+ → New repository**. Usa el nombre `mi-practica-git`, elige visibilidad y marca **Add a README file**. Pulsa **Create repository**. Para aprender, puedes usar un repositorio privado.

No necesitas hacer fork del repositorio de la docente. Puedes copiar las plantillas `mi-proyecto.md` y `bitacora.md` de este material a tu repositorio mediante **Add file → Create new file**. Confirma cada archivo con un mensaje descriptivo.

## 2. Completa la ficha

Elige la [ruta gráfica](docs/02-interfaz-grafica.md) o la [ruta de consola](docs/03-consola.md). Realiza estos cambios por separado:

1. Completa el título, tu nombre y una descripción en `mi-proyecto.md`. Commit: `Completa la ficha personal`.
2. Añade una imagen propia a `images/mi-imagen.jpg` y enlázala desde la ficha. Usa la extensión real de tu archivo. Commit: `Añade una imagen al proyecto`.
3. Actualiza la descripción y añade una fuente consultada. Commit: `Actualiza la descripción y la fuente`.
4. Crea `notas.md` con dos ideas nuevas. Commit: `Añade notas personales`.
5. Renombra ese archivo a `ideas.md`. Commit: `Renombra las notas como ideas`.
6. Borra `ideas.md`. Commit: `Elimina el archivo de ideas`.

Después de cada commit local, haz push y comprueba el resultado en GitHub. Las ediciones web ya están en GitHub.

## 3. Provoca y corrige un error

Con los cambios anteriores guardados y publicados, sustituye el título de la ficha por `TÍTULO EQUIVOCADO`. Haz un commit exclusivo para ese cambio y publícalo. Deshazlo con **Revert Changes in Commit** en GitHub Desktop o `git revert --no-edit HEAD` desde consola. Publica la corrección y comprueba que vuelve el título anterior y que el commit erróneo sigue visible en el historial.

Repite con otro error si quieres practicar la otra interfaz. Consulta [la guía de recuperación](docs/05-recuperar-versiones.md).

## 4. Prueba otro entorno

Abre tu repositorio en VS Code o sigue la [guía de Colab](docs/04-colab.md). Añade en `bitacora.md` qué entorno utilizaste y qué aprendiste. Guarda, confirma y publica.

## Lista de comprobación

- [ ] El repositorio pertenece a mi cuenta.
- [ ] Sé diferenciar Git, GitHub, guardar, add, commit y push.
- [ ] He creado, actualizado, renombrado y eliminado archivos.
- [ ] La imagen se ve correctamente en GitHub.
- [ ] Veo los commits y entiendo sus mensajes.
- [ ] He deshecho un error publicado conservando el historial.
- [ ] He usado al menos una interfaz gráfica y una terminal.
- [ ] No he subido contraseñas, tokens ni archivos privados.

Evidencia opcional para entregar: enlace al repositorio y hashes del commit del error y del commit que lo revierte. Si es privado, concede acceso a la docente solo si te lo solicita.

[Volver al inicio](README.md)
