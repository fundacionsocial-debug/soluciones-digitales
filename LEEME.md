# Mi Página — propuesta interactiva

Esto reemplaza el PDF de presentación. Es **una página** que:

1. Al abrirla, le pide a la persona escoger entre **Página Web** o **Sistema Administrativo**.
   Toda la página se adapta a lo que elija.
2. La ayuda a descubrir qué quiere, con un configurador y una **vista previa en vivo**
   (un celular con su página, o un panel con sus módulos y sus cifras).
3. Al final le entrega **la propuesta en PDF** y un resumen listo para mandarte por WhatsApp.

**Enlace para mandar a la gente:**

```
https://soluciones-digitales-eosin.vercel.app
```

- Repositorio (público): https://github.com/fundacionsocial-debug/soluciones-digitales
- Proyecto en Vercel: `soluciones-digitales`, en tu cuenta `fundacionsocial-debug`.

---

## 1. Verla en tu computador

Doble clic en **`index.html`**. Se abre en tu navegador y funciona sin internet.

---

## 2. Lo único que DEBES cambiar: tu WhatsApp

Abre `index.html` con el Bloc de notas (clic derecho → *Abrir con* → *Bloc de notas*),
busca con `Ctrl+B` la palabra `whatsapp` y verás:

```
whatsapp : "57XXXXXXXXXX",
```

Cambia las `X` por tu número: **indicativo del país + número, sin `+`, sin espacios,
sin guiones**. Colombia es `57`.

Ejemplo: si tu número es 300 123 4567 → `"573001234567"`

Guarda con `Ctrl+G`.

> Mientras diga `XXXXXXXXXX`, los botones de WhatsApp funcionan igual pero abren el
> **correo** en vez del chat. No se rompe nada.

---

## 3. Cambiar los precios

En el mismo archivo, justo debajo, hay **dos listas de precios**: una para páginas web
(`web:`) y otra para sistemas (`sistema:`). Cada nivel se ve así:

```
1:{ nombre:"Presencia", desde:450000,
    rango:"$450.000 – $650.000 COP",
```

- `rango` es el texto que ve la persona.
- `desde` es un número que la página usa para avisar cuando el presupuesto de la persona
  queda por debajo. **Si cambias el `rango`, cambia también el `desde`.**

### Ojo con estos dos rangos

De la conversación original quedaron definidos: página web 450–650k / 700k–1.1M / desde 1.5M,
y sistema completo 6 a 10 millones. Las **dos primeras etapas del sistema**
($1.500.000–$2.500.000 y $2.500.000–$5.000.000) son una interpolación entre esos dos
extremos: revísalas y ajústalas a lo que de verdad quieres cobrar.

---

## 4. Cambiar el nombre de la segunda ruta

Se llama **"Sistema Administrativo"** a propósito, y no *"programa contable"*:

- En Colombia, decir "contable" hace pensar en contabilidad legal, NIIF y reportes a la DIAN.
  Eso lo hace un contador público, no un sistema. Prometerlo te metería en un problema.
- "Sistema Administrativo" es lo que de verdad es: organiza la operación, los clientes,
  los cobros y el dinero del negocio.
- Hay una pregunta frecuente dentro de la página que dice explícitamente que **no reemplaza
  al contador**. No la borres: es lo que te protege y además genera confianza.

Si quieres cambiarle el nombre, aparece en tres sitios del archivo: el título de la tarjeta
en la portada, el botón "Sistema" de la barra de arriba y los textos del hero.

---

## 5. Las imágenes

Están en `assets/`:

| Archivo | Para qué |
|---|---|
| `og-card.jpg` | La imagen que aparece cuando mandas el enlace por WhatsApp |
| `portada-web.jpg` | Tarjeta de la ruta "Página Web" |
| `portada-sistema.jpg` | Tarjeta de la ruta "Sistema Administrativo" |
| `hero.jpg` | Fondo del encabezado |
| `trabajos.jpg` | Banda de la sección "Lo que ya funciona" |

Los PNG originales (sin comprimir, 8 MB) quedaron en `assets/originales/` **solo en tu
computador** — no se suben al repositorio. Las que usa la web son los `.jpg`, que juntos
pesan 441 KB para que la página cargue rápido con datos móviles.

> Si cambias `og-card.jpg`, WhatsApp guarda la imagen anterior en memoria un rato.
> Para forzar que la actualice, cámbiale el nombre del archivo (y actualiza las dos
> etiquetas `og:image` y `twitter:image` del `<head>`).

---

## 6. El PDF

No usa ninguna librería: la página tiene una **hoja de propuesta oculta** que solo aparece
al imprimir. Cuando la persona toca *"Descargar la propuesta en PDF"*, se abre la ventana
de impresión del navegador y escoge **"Guardar como PDF"**.

Funciona igual en computador y en celular, y el PDF sale en blanco, con tipografía legible
y en una sola hoja tamaño carta/A4. Incluye los datos del interesado, lo que pidió, el nivel
sugerido, el rango y una advertencia de que no es una cotización en firme.

---

## 7. Publicar un cambio

Ya está conectado a GitHub: **cada vez que subas un cambio, Vercel publica solo.**

```bash
git add -A
git commit -m "lo que cambiaste"
git push
```

En un minuto el enlace muestra la versión nueva.

---

## 8. Detalles técnicos

- Un solo `index.html` + la carpeta `assets/`. Sin librerías, sin build, sin servidor.
- Funciona en celular, tablet y computador, sin scroll horizontal.
- Lo que la persona escribe se guarda **en su propio dispositivo**. No te llega nada
  hasta que ella toca el botón de WhatsApp o genera el PDF.
- Respeta la opción de "reducir movimiento" del sistema, para quien se marea con animaciones.
