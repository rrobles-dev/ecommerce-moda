# Neo Vetro · Prototipo de e-commerce

Prototipo visual y responsive de la tienda online de **Neo Vetro**, una marca de anteojos unisex con sede en París e inspiración de diseño italiana. Proyecto del bootcamp 4Geeks Academy (módulo *Command Line, Git and GitHub*).

🔗 **Sitio publicado:** https://rrobles-dev.github.io/ecommerce-moda/

## Vistas

| Vista | Archivo | Contenido |
|---|---|---|
| Home | `index.html` | Navbar (logo, búsqueda, menú de cuenta), hero de campaña, *Nuevos lanzamientos*, *Más vendidos*, footer |
| Catálogo | `catalogo.html` | Filtros por categoría y talla de montura, grilla 4×5 (20 productos) |
| Producto | `producto.html` | Dos columnas (imagen + datos: nombre, código, talla, precio, cantidad, *Agregar al carrito*), descripción con materiales y uso recomendado |
| Carrito | `carrito.html` | 3 productos de ejemplo (miniatura, precio unitario, cantidad, total), resumen con subtotal, impuestos y total, botón *Comprar* |
| Checkout | `checkout.html` | Flujo en 3 pasos: datos personales, dirección de entrega y pago con tarjeta |

## Decisiones

- **Producto:** la marca es de anteojos, un accesorio de moda. Cada requisito del enunciado tiene su equivalente: la *talla* es el ancho de la montura (S/M/L) y las categorías son ópticos, sol, luz azul y accesorios.
- **Mercado:** la tienda vende en Chile, así que los precios están en CLP con IVA incluido. El carrito desglosa *subtotal neto + IVA 19% = total*.
- **Navbar y footer reutilizados:** sin JavaScript no hay *includes*, así que son bloques idénticos en las 5 vistas, marcados con comentarios `NAVBAR` y `FOOTER`.
- **Sin JavaScript propio:** el menú de cuenta usa `<details>` nativo; filtros y formularios son HTML.
- **Checkout seguro por diseño:** los campos no tienen `name`, así que el prototipo no envía datos. En producción, la tarjeta la captura la pasarela de pago, nunca nuestro servidor.
- **Imágenes:** ilustraciones SVG propias (menos de 1 KB cada una, sin licencias). La imagen principal carga con prioridad y el resto en diferido (`loading="lazy"`).
- **SEO:** HTML semántico, un `h1` por vista, meta descriptions y Schema.org (`Organization` en la home, `Product` en la vista de producto).

## Tecnologías

HTML5 · Tailwind CSS v4 (CDN) · Schema.org (JSON-LD) · Git y GitHub · GitHub Pages

## Cómo ejecutarlo en local

```bash
pip3 install flask && python3 server.py
```

Abre http://localhost:3000

## Flujo de trabajo con Git

Una rama por vista (`feature/home`, `feature/catalogo`, `feature/producto`, `feature/carrito`, `feature/checkout`). Cada una se integró a `main` mediante un pull request, después de actualizarla con `git pull origin main`.

## Rendimiento

Resultado de PageSpeed Insights sobre la URL publicada:

![Resultado de PageSpeed](pagespeed-result.png)
