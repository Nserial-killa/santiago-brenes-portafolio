# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Descripción del proyecto

Portafolio digital de **Santiago Brenes**, estudiante de Ingeniería Informática. El sitio está orientado a postular pasantías en startups y empresas corporativas, con foco en desarrollo backend y frontend.

## Estructura del proyecto

```
/
├── index.html                # Sitio completo (HTML + CSS + JS en un solo archivo)
└── assets/
    ├── santiago-perfil.jpg   # Foto de perfil
    └── cv/
        ├── cv-es.docx        # CV en español
        └── cv-en.docx        # CV en inglés
```

No hay build ni package manager: para previsualizar, basta con abrir `index.html` en el navegador o servirlo con cualquier servidor estático (`python3 -m http.server`).

## Tecnologías

- HTML, CSS y JavaScript vanilla — sin frameworks ni dependencias externas
- Desplegable directamente en **GitHub Pages** (rama `main`, carpeta raíz)

## Diseño

- Estilo corporativo oscuro, paleta morado (`#6B4FC8`) sobre negro (`#0B0B13`); tokens de color en `:root` al inicio del `<style>`
- Bilingüe ES/EN con toggle en la navegación (botones `.lang-btn`, función `setLang()`)
- Responsive: colapsa a una sola columna en pantallas menores a 700px
- Animaciones de scroll suaves vía `IntersectionObserver` (clase `.reveal`), respeta `prefers-reduced-motion`

## Secciones (`index.html`)

| ID | Contenido |
|---|---|
| `#inicio` | Hero con nombre, descripción y CTAs |
| `#sobre-mi` | Foto y párrafos de presentación |
| `#habilidades` | 4 tarjetas de tecnologías por categoría |
| `#proyectos` | 2 tarjetas de proyectos (completado + en proceso) |
| `#cv` | Descarga de CV (ES e EN) |
| `#contacto` | Links a correo, LinkedIn, GitHub y WhatsApp |

## Cómo editar el contenido bilingüe

Cada elemento de texto tiene un atributo `data-i18n="clave"` y su contenido en español está escrito directamente en el HTML como fallback estático. El objeto `i18n` (dentro del `<script>` al final de `index.html`) contiene las traducciones ES/EN reales que `setLang()` inyecta en tiempo de ejecución.

**Al editar un texto hay que actualizar ambos lugares**: el contenido del elemento en el HTML (lo que se ve antes de que corra el JS, y el fallback si la clave no existe en `i18n`) y la entrada correspondiente en `i18n.es` / `i18n.en`. Si solo se edita uno de los dos, el texto se verá distinto según el idioma activo o el momento de carga.

## Pendiente de completar

- [ ] Los links de proyectos apuntan al perfil de GitHub genérico (`github.com/sanbrenmo`) en vez de a los repos específicos; buscar `REEMPLAZAR` en `index.html` para ubicar los títulos, descripciones, stacks y links de placeholder en `#proyectos`
- [ ] Los `href` de descarga de CV en `#cv` apuntan a `cv/cv-es.pdf` / `cv/cv-en.pdf`, pero los archivos reales están en `assets/cv/cv-es.docx` y `assets/cv/cv-en.docx` — los links de descarga están rotos hasta corregir la ruta/extensión

## Despliegue en GitHub Pages

1. Subir el repositorio a GitHub
2. Ir a **Settings → Pages**
3. Seleccionar fuente: rama `main`, carpeta `/ (root)`
4. El sitio quedará disponible en `https://sanbrenmo.github.io/<nombre-del-repo>/`
