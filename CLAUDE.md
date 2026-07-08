# CLAUDE.md

## Descripción del proyecto

Portafolio digital de **Santiago Brenes**, estudiante de Ingeniería Informática. El sitio está orientado a postular pasantías en startups y empresas corporativas, con foco en desarrollo backend y frontend.

## Estructura del proyecto

```
/
├── index.html        # Sitio completo (HTML + CSS + JS en un solo archivo)
├── photo.jpg         # Foto profesional (agregar)
└── cv/
    ├── cv-es.pdf     # CV en español (agregar)
    └── cv-en.pdf     # CV en inglés (agregar)
```

## Tecnologías

- HTML, CSS y JavaScript vanilla — sin frameworks ni dependencias externas
- Sin sistema de build ni package manager
- Desplegable directamente en **GitHub Pages** (rama `main`, carpeta raíz)

## Diseño

- Estilo corporativo oscuro, paleta morado (`#6B4FC8`) sobre negro (`#0B0B13`)
- Bilingüe ES/EN con toggle en la navegación — todas las cadenas de texto están en el objeto `i18n` al final del `<script>`
- Responsive: colapsa a una sola columna en pantallas menores a 700px
- Animaciones de scroll suaves (`IntersectionObserver`), respeta `prefers-reduced-motion`

## Secciones

| ID | Contenido |
|---|---|
| `#inicio` | Hero con nombre, descripción y CTAs |
| `#sobre-mi` | Foto y párrafos de presentación |
| `#habilidades` | 4 tarjetas de tecnologías por categoría |
| `#proyectos` | 2 tarjetas de proyectos (completado + en proceso) |
| `#cv` | Descarga de CV en PDF (ES e EN) |
| `#contacto` | Links a correo, LinkedIn, GitHub y WhatsApp |

## Pendiente de completar

- [ ] Reemplazar el SVG placeholder por `<img src="photo.jpg" alt="Santiago Brenes">` en `#sobre-mi`
- [ ] Actualizar títulos, descripciones y links de los proyectos (buscar `REEMPLAZAR` en el HTML)
- [ ] Actualizar las etiquetas `skill-tag` con las tecnologías reales
- [ ] Agregar `cv/cv-es.pdf` y `cv/cv-en.pdf`
- [ ] Apuntar los `href` de los repositorios a los repos específicos de cada proyecto

## Cómo editar el contenido bilingüe

Todo el texto del sitio vive en el objeto `i18n` dentro del `<script>` al final de `index.html`. Para cambiar cualquier texto, solo hay que editar el valor correspondiente en `es` o `en` sin tocar el HTML.

## Despliegue en GitHub Pages

1. Subir el repositorio a GitHub
2. Ir a **Settings → Pages**
3. Seleccionar fuente: rama `main`, carpeta `/ (root)`
4. El sitio quedará disponible en `https://sanbrenmo.github.io/<nombre-del-repo>/`
