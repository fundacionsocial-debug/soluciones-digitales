# Soluciones digitales — propuesta interactiva

Página de presentación comercial de servicios de desarrollo web y sistemas a medida.

En vez de un PDF, es una página que:

- **se demuestra a sí misma** — la página es la muestra del trabajo;
- **acompaña al cliente a descubrir qué necesita**, con un configurador guiado;
- **arma una vista previa en vivo** del sitio del cliente con su propio nombre, su rubro
  y la paleta que elija;
- **genera un resumen listo para enviar** por WhatsApp, correo o descarga.

## Cómo está hecho

Un solo archivo: [`index.html`](index.html).

- Sin librerías, sin build, sin dependencias, sin backend.
- HTML, CSS y JavaScript nativos. Todo el CSS y el JS van dentro del archivo.
- Diseño adaptable (celular, tablet, computador) y sin scroll horizontal.
- Accesible: navegación por teclado, `aria-live` en el resultado y respeto por
  `prefers-reduced-motion`.
- Lo que el visitante escribe se guarda **solo en su propio dispositivo**
  (`localStorage`). No se envía nada a ningún servidor: el resumen viaja únicamente
  cuando la persona decide tocar el botón.

## Configuración

Todo lo editable está en el bloque `CONFIG`, al inicio del `<script>`: nombre, WhatsApp,
correo y los rangos de inversión de cada nivel. Ver [`LEEME.md`](LEEME.md) para el detalle.

## Publicación

Es una página estática: se despliega tal cual, sin comandos de build.
