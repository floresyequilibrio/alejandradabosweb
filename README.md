# alejandradabos-web

Sitio web oficial de Alejandra Dabos · Real Mind Method™  
→ [alejandradabos.com](https://alejandradabos.com)

---

## Estructura

```
/
├── index.html                  ← Sitio principal (servicios, método, libro, artículos)
├── c-suite.html                ← Sección C-Suite / Executive Brain Partner
├── articulos.html              ← Índice del blog (lista dinámica desde JSON)
├── articulo.html               ← Template genérico para cualquier carta individual
├── libro.html                  ← El Impuesto Invisible del Liderazgo (landing del libro)
├── conferencias.html           ← Kit oradora — conferencias y workshops para C-Suite
├── politica-privacidad.html    ← Política de Privacidad
├── terminos-condiciones.html   ← Términos y Condiciones
├── img/
│   ├── portada-libro.png       ← Portada de El Impuesto Invisible del Liderazgo
│   └── alejandra-portrait.jpg  ← Retrato profesional (usado en libro.html y conferencias.html)
└── articulos/
    ├── index.json                          ← Manifest con la metadata de todas las cartas
    ├── mapa-de-la-decision.md
    ├── neurobiologia-del-presente.md
    ├── sindrome-del-impostor.md
    ├── sesgos-cognitivos-inversiones.md
    ├── decir-no-sin-culpa.md
    ├── biohacking-del-lenguaje.md
    ├── procrastinacion-no-es-pereza.md
    └── ansiedad-brujula-interna.md
```

---

## Navegación

| URL | Página |
|-----|--------|
| `/` | Inicio — servicios, método, libro, sobre mí, artículos |
| `/c-suite.html` | Posicionamiento C-Suite — Executive Brain Partner |
| `/articulos.html` | Todas las Cartas del Método (lista dinámica) |
| `/articulo.html?slug=[slug]` | Carta individual (renderizada desde `.md`) |
| `/libro.html` | El Impuesto Invisible del Liderazgo — landing del libro |
| `/conferencias.html` | Kit oradora — conferencias y workshops |
| `/politica-privacidad.html` | Política de Privacidad |
| `/terminos-condiciones.html` | Términos y Condiciones |

Nav unificado en todas las páginas (excepto `c-suite.html`, que mantiene su propio funnel con CTA "Aplicar"):
`Método · Transformación · Servicios · Preguntas · Sobre mí · El libro · Artículos · Conferencias · C-Suite → · [Agendar Diagnóstico]`

---

## Enlaces externos

- **Libro (Hotmart)**: `https://go.hotmart.com/F106521852G?dp=1`
- **CTA Conferencias**: `mailto:contacto@alejandradabos.com` (con subject y cuerpo pre-armado)
- **CTA Diagnóstico**: `https://wa.me/5492234973418`
- **CTA C-Suite**: `https://form.alejandradabos.com/`

---

## Sistema de artículos dinámico

Cada carta es un archivo `.md` dentro de `/articulos/`. La lista y el contenido se generan en el navegador desde `articulos/index.json`.

### Cómo agregar una carta nueva

**1.** Crear `/articulos/nombre-carta.md` con frontmatter YAML:

```markdown
---
slug: nombre-carta
number: 09
title: Título de la carta
subtitle: Un subtítulo breve
readTime: 6 min
description: Descripción para meta tag (SEO).
excerpt: Bajada que aparece en el card de la lista.
---

Contenido de la carta en Markdown.

## Un subtítulo

**Negrita**, *itálica*, [links](url), citas con `>`.

<div class="impact">Frase de impacto centrada.</div>
```

**2.** Agregar la entrada al final del array en `/articulos/index.json`:

```json
{
  "slug": "nombre-carta",
  "number": "09",
  "title": "Título de la carta",
  "subtitle": "Un subtítulo breve",
  "excerpt": "Bajada que aparece en el card...",
  "readTime": "6 min",
  "description": "Descripción para meta tag.",
  "cardTitle": "Título completo tal como debe verse en el card"
}
```

**3.** Subir a GitHub. La carta aparece automáticamente en `articulos.html` y es navegable en `articulo.html?slug=nombre-carta`.

### Cambios de diseño

Todo el diseño de las cartas está en `articulo.html`. Cualquier cambio ahí se aplica a las 8+ cartas automáticamente.

---

## Pendiente — Newsletter MailerLite

En `index.html` y `articulos.html`, buscar el comentario `REEMPLAZAR con endpoint MailerLite` y reemplazar la URL con el endpoint real del formulario embebido de MailerLite.

---

## Tecnología

- HTML / CSS / JS puros — sin frameworks ni dependencias
- Tipografía: Cormorant Garamond + DM Sans (Google Fonts)
- Renderer de Markdown: [marked.js](https://marked.js.org/) vía CDN
- Hosting: Hostinger (conectado vía Git)
- Dominio: alejandradabos.com

---

© 2026 Alejandra Dabos · Real Mind Method™
