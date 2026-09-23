# Todo Cosas — Tienda online

Catálogo interactivo de productos (herramientas, pinturas de piscina, motores de portón, etc.) con pedido directo por WhatsApp.

## Cómo funciona
- `tienda.html` es un archivo único y autocontenido (HTML + CSS + JS).
- El cliente filtra por categoría, elige cantidad (limitada por el stock) y al tocar "Pedir por WhatsApp" se abre un chat con el mensaje armado hacia el número configurado en el código (`const WHATSAPP`).
- El panel de administrador permite agregar, editar y eliminar productos.

## ⚠️ Importante si lo hosteas fuera de Claude (GitHub Pages, etc.)
El panel de admin usa `claude.use("artifact")` y `claude.use("user")`, funciones que **solo existen cuando la página corre como Artifact de Claude**. Fuera de ese entorno (GitHub Pages, Netlify, tu propio hosting):
- El catálogo se va a ver perfecto, con los productos que tenía cargados al momento de exportar el archivo.
- El botón de admin no va a aparecer y los cambios no se van a guardar en ningún lado (no hay backend).

Si quieres que el panel de admin funcione fuera de Claude, hay que reemplazar esa parte por algo como `localStorage` (solo guarda en el navegador de quien lo edita) o una base de datos real (Firebase, Supabase, etc.). Puedo ayudarte a armar esa versión si te sirve.

## Subir a GitHub
1. Crea un repositorio nuevo en https://github.com/new (márcalo como público para que quede abierto).
2. Sube `tienda.html` (y este `README.md`) arrastrándolos en la página del repo, o con:
   ```bash
   git init
   git add .
   git commit -m "Tienda inicial"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
   git push -u origin main
   ```
3. (Opcional) Activa GitHub Pages en Settings → Pages → Branch: main, para tener una URL pública tipo `https://TU_USUARIO.github.io/TU_REPO/tienda.html`.

## Licencia
MIT — libre de usar, copiar y modificar.
