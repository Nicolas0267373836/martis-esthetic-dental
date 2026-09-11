# Martis Esthetic & Dental Clinic Group — sitio web

Sitio estático (HTML + CSS + JS, sin frameworks ni build) para la clínica
**Martis Esthetic & Dental Clinic Group**, San Pedro de Macorís, República
Dominicana. Listo para abrir directamente en el navegador o desplegar en
cualquier hosting estático (Vercel, Netlify, GitHub Pages, etc.).

## Estructura del proyecto

```
martis-site/
├── index.html      → Todo el contenido y la estructura semántica del sitio
├── styles.css      → Estilos (variables de color en :root + reglas por sección)
├── script.js       → Menú móvil (abrir/cerrar) y año dinámico del footer
├── images/         → Fotografías e imágenes de marca (ver tabla abajo)
└── README.md       → Este archivo
```

No hay imágenes incrustadas en base64: todas las rutas en `index.html` y
`styles.css` son relativas a la carpeta `images/`.

## Cómo verlo

Abre `index.html` directamente en un navegador, o sirve la carpeta con
cualquier servidor estático, por ejemplo:

```bash
npx serve .
```

## Despliegue en Vercel

Este proyecto está preparado como sitio estático: no necesita instalar
dependencias, un comando de build ni variables de entorno. `vercel.json`
mantiene URLs limpias y sin barra final.

Para crear una vista previa desde esta carpeta, ejecuta:

```bash
vercel
```

Vercel detectará `index.html` en la raíz. Cuando la vista previa esté aprobada,
publícala en producción con:

```bash
vercel --prod
```

La carpeta `.vercel/` queda ignorada porque contiene el enlace local a una
cuenta y proyecto de Vercel; no debe subirse al repositorio.

## Imágenes requeridas (carpeta `images/`)

| Archivo | Uso en el sitio | Origen |
|---|---|---|
| `logo-icono.png` | Ícono de marca en el nav y favicon | Recortado del logo original proporcionado por la clínica |
| `logo-wordmark.png` | Wordmark "MARTIS ESTHETIC & DENTAL CLINIC GROUP" (disponible como asset de marca; no usado en `index.html` actualmente) | Recortado del logo original proporcionado por la clínica |
| `logo-completo.png` | Logo completo (ícono + wordmark), asset de marca de respaldo | Logo original proporcionado por la clínica |
| `hero-equipo.jpg` | Foto principal de la sección de portada (Hero) | Fotografía real proporcionada por la clínica |
| `antes-despues-1.jpg` | Primer caso en la sección "Antes y Después" | Fotografía real proporcionada por la clínica |
| `antes-despues-2.jpg` | Segundo caso en la sección "Antes y Después" | Fotografía real proporcionada por la clínica |
| `antes-despues-3.jpg` | Tercer caso en la sección "Antes y Después" | Fotografía real proporcionada por la clínica |

Todas las imágenes ya están incluidas en esta carpeta. Si se reemplazan por
versiones nuevas, respeta los mismos nombres de archivo (o actualiza las
rutas correspondientes en `index.html`).

**Pendiente de confirmar con la clínica antes de producción:** la
autorización vigente de cada paciente para publicar las fotos de
"Antes y Después" (ver nota de texto en esa misma sección del sitio).

## Variables de color (`styles.css`, bloque `:root`)

| Variable | Valor | Uso |
|---|---|---|
| `--color-graphite` | `#211d18` | Texto principal, fondos oscuros (nav, footer, botones outline oscuros) |
| `--color-graphite-dark` | `#18140f` | Fondo del footer |
| `--color-ivory` | `#faf7f0` | Fondo general del sitio |
| `--color-ivory-alt` | `#f8f3e9` | Fondo del `<html>` detrás del contenido |
| `--color-stone` | `#f1ece0` | Fondo alterno de secciones |
| `--color-gold` | `#c9a24c` | Color de marca / acento principal (botones, iconos) |
| `--color-gold-hover` | `#d6b566` | Acento en estado hover |
| `--color-gold-dark` | `#b3872f` | Enlaces de texto |
| `--color-gold-darker` | `#9c7a2d` | Iconos de servicios sobre fondo dorado claro |
| `--color-text` | `#2b2621` | Texto de cuerpo |
| `--color-text-muted` | `#4a4237` | Enlaces de navegación |
| `--color-text-soft` | `#6b5f4f` | Texto secundario (subtítulos de sección) |
| `--color-label` | `#8a7a5c` | Etiquetas pequeñas en mayúsculas (Antes/Después, meta de reseñas) |
| `--color-whatsapp` | `#2f7a52` | Botón flotante de WhatsApp |
| `--color-white` | `#fff` | Fondos blancos (tarjetas) |

Estos colores están derivados del logo real de la clínica (paleta grafito +
dorado champán). Cambiar solo estas variables permite reutilizar el archivo
como base para otro cliente de la especialidad "Dentista".

Tipografías (Google Fonts, cargadas en `<head>`): **Fraunces** (serif, para
títulos) y **Manrope** (sans-serif, para cuerpo de texto y UI).

## Enlaces y datos de contacto usados en el sitio

| Dato | Valor | Fuente |
|---|---|---|
| Instagram | https://www.instagram.com/martis_dental_clinic_group | Perfil oficial de la clínica |
| WhatsApp (agendar cita) | https://wa.me/message/V6QXEHWZOQPND1 | Enlace de WhatsApp Business proporcionado |
| Teléfono | +1 829-813-0938 | Proporcionado por la clínica |
| Dirección | Av. 27 de Febrero esq. Profesor Puello #56, San Pedro de Macorís, República Dominicana | Proporcionada por la clínica |
| Horario | Lunes a viernes: 9 a. m.–12 p. m. y 1–7 p. m.; sábados y domingos: cerrado | Proporcionado por la clínica |
| Enlace "Cómo llegar" | Google Maps (búsqueda por dirección, sin API key) | Generado a partir de la dirección real |
| Turismo dental | Alianza con Smile & Paradise Travel (@smileparadiserd) | Proporcionado por la clínica |
| Reseñas de pacientes | Ruben Lopez, Richard Payano, Veronica Mesa Perez (citas textuales) | Proporcionadas directamente por la clínica |

## Notas técnicas

- HTML semántico: `<header>`, `<main>`, `<section>` por bloque de
  contenido, `<footer>`, botón accesible (`aria-expanded`,
  `aria-controls`) para el menú móvil.
- `script.js` solo controla comportamiento (abrir/cerrar menú móvil,
  año dinámico en el copyright) — no genera ni modifica contenido.
- Sin build ni dependencias de paquetes: se puede editar y previsualizar
  directamente.
- Fuente de referencia de diseño original: plantilla "Estándar Dentista"
  de WebDom, adaptada con la identidad real de Martis Esthetic & Dental
  Clinic Group.
