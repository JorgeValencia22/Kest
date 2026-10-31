# KEST — sitio estático

Tienda de KEST lista para GitHub Pages: `index.html` + `img/` + `brand/` + `config.js`. No necesita servidor ni base de datos.

## Subir a GitHub Pages

1. Crea un repositorio en GitHub y sube **el contenido de esta carpeta** (no la carpeta misma), de modo que `index.html` quede en la raíz.
2. En el repositorio: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**.
3. En un minuto el sitio queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

## Antes de publicar

Edita `config.js` y completa tus datos:

```js
window.KEST_CONFIG = {
  whatsapp: "56912345678", // código de país, sin "+"
  email: "contacto@tudominio.cl",
  instagram: "https://instagram.com/tu_cuenta",
};
```

Con WhatsApp configurado, el botón del carrito abre un chat con el pedido ya escrito. Sin él, el botón copia el pedido.

## Cómo funciona

- Catálogo, ficha de producto, carrito (se guarda en el navegador) y búsqueda funcionan sin servidor.
- **No hay pago en línea.** El cliente envía el pedido y tú coordinas pago y entrega con él.
- El stock no se controla en este sitio: es una vitrina.
- Muestra solo los productos que tienen foto.

## Actualizar productos

Los productos salen del panel de la tienda (`data/db.json`). Para regenerar esta carpeta, en la raíz del proyecto:

```bash
node scripts/build-static.mjs
```

Luego vuelve a subir `index.html` e `img/` a GitHub. `config.js` no se pisa si no lo reemplazas.
