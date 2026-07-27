# Propuesta de servicios web — página interactiva

Esto reemplaza el PDF. Es **una sola página** que:

1. Le muestra a la persona lo que puedes hacer (la página misma es la demostración).
2. La ayuda a descubrir qué quiere, con un configurador y una **vista previa en vivo** que
   se arma con el nombre de su negocio.
3. Te manda el resumen por **WhatsApp**, ya escrito, para que tú solo cotices.

---

## 1. Verla

Doble clic en **`index.html`**. Se abre en tu navegador. Funciona sin internet.

---

## 2. Lo único que DEBES cambiar: tu WhatsApp

Abre `index.html` con el Bloc de notas (clic derecho → *Abrir con* → *Bloc de notas*),
busca con `Ctrl+B` la palabra `whatsapp` y verás esto:

```
whatsapp : "57XXXXXXXXXX",
```

Cambia las `X` por tu número: **indicativo del país + número, sin `+`, sin espacios,
sin guiones**. Colombia es `57`.

Ejemplo: si tu número es 300 123 4567 → `"573001234567"`

Guarda con `Ctrl+G`.

> Mientras diga `XXXXXXXXXX`, los botones de WhatsApp funcionan igual pero abren el **correo**
> en vez del chat. No se rompe nada.

---

## 3. Cambiar los precios

En el mismo archivo, un poco más abajo, está la lista de niveles:

```
1:{ nombre:"Presencia", desde:450000,
    rango:"$450.000 – $650.000 COP",
```

- `rango` es el texto que ve la persona.
- `desde` es solo un número que la página usa para avisar cuando el presupuesto
  de la persona queda por debajo. Si cambias el `rango`, cambia también el `desde`.

Los tres niveles están juntos, uno debajo del otro. No toques nada más de esa zona.

---

## 4. Ya está publicada

**Enlace para mandar a la gente:**

```
https://soluciones-digitales-eosin.vercel.app
```

- Repositorio (público): https://github.com/fundacionsocial-debug/soluciones-digitales
- Proyecto en Vercel: `soluciones-digitales`, en tu cuenta `fundacionsocial-debug`.

> El `-eosin` lo puso Vercel porque `soluciones-digitales.vercel.app` ya lo tenía
> otra persona. Si algún día compras tu propio dominio (por ejemplo
> `sebastianlopez.co`), se conecta a este mismo proyecto y el enlace queda limpio.

### Cómo publicar un cambio

Ya está conectado a GitHub: **cada vez que subas un cambio al repositorio, Vercel
publica solo.** No hay que hacer nada más.

Si lo haces desde esta carpeta, son tres órdenes:

```bash
git add -A
git commit -m "lo que cambiaste"
git push
```

En un minuto el enlace ya muestra la versión nueva.

No necesita configuración: es una página estática, sin base de datos y sin servidor.

---

## 5. Lo que la persona te va a enviar

Cuando llena el configurador y toca *Enviármelo por WhatsApp*, te llega un mensaje así:

```
Hola Sebastián, llené el formulario de tu página. Este es mi resumen:

Negocio: Delicias Diana
Se dedica a: Postres y tortas por encargo en Cali
Estilo que me gusta: Cálido y cercano
Quiero lograr: Que me encuentren en internet, Vender más
Me gustaría que tuviera: Botón de WhatsApp, Catálogo con precios, Agenda de citas
Cuándo: En 1 o 2 meses
Presupuesto: $700.000 a $1.500.000

La página me sugirió: Nivel 2 · Profesional ($700.000 – $1.100.000 COP)

Mi nombre: Diana Restrepo
Mi contacto: 300 123 4567
```

Con eso ya tienes todo para cotizar sin una sola reunión previa.

---

## 6. Detalles técnicos (por si algún día los necesitas)

- Un solo archivo, sin librerías externas, sin cuentas, sin costos.
- Funciona en celular, tablet y computador.
- Lo que la persona escribe se guarda **en su propio celular** (no te llega nada
  hasta que ella toca el botón). No recoge datos a escondidas.
- Respeta la opción de "reducir movimiento" del sistema, para quien se marea con animaciones.
