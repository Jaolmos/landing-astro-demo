# AGENTS.md

## Resumen del Proyecto

Landing page de demostración con Astro para "NovaTech Studio" (contenido en español).

## Datos Clave

- **Framework**: Astro v6.1.10, TypeScript (modo estricto)
- **Node**: Se requiere >=22.12.0
- **No hay tests, linting, CI ni pre-commit hooks** - no buscar
- **Idioma**: Todo el contenido visible está en español (`lang="es"`)

## Comandos

```bash
npm install          # Instalar dependencias
npm run dev          # Servidor de desarrollo en localhost:4321
npm run build        # Compilar a ./dist/
npm run preview      # Vista previa del build de producción
```

## Arquitectura

```
/
├── src/
│   ├── pages/index.astro        # Página principal (única)
│   ├── layouts/Layout.astro     # Layout raíz (meta tags SEO, structured data, JS scroll reveal)
│   ├── components/              # Componentes de sección (Header, Hero, Services, etc.)
│   ├── components/ui/           # UI reutilizable (Button, Card, SectionTitle)
│   └── styles/global.css        # Estilos globales
├── public/
│   ├── favicon.svg              # Favicon
│   ├── robots.txt               # Directivas para crawlers
│   └── sitemap.xml              # Sitemap XML
└── .agents/                     # Skills de opencode
```

## SEO

- **Meta tags**: robots, author, canonical URL, Open Graph, Twitter Cards (en `Layout.astro`)
- **Structured data (JSON-LD)**: Organization, WebSite (en `Layout.astro`), FAQPage (en `FAQ.astro`)
- **Archivos técnicos**: `robots.txt` y `sitemap.xml` en `public/`
- **URL canónica**: `https://novatechstudio.com`

## Patrones

- Los componentes usan la clase `.reveal` + IntersectionObserver en `Layout.astro` para animaciones de scroll
- Layout acepta props `title` y `description` (opcional)
- Sin framework de cliente (Astro puro)

## Commits

Usar prefijos en español:

- `feat:` - Nueva funcionalidad
- `style:` - Cambios de estilos (CSS, diseño visual)
- `fix:` - Corrección de errores
- `refactor:` - Refactorización de código
- `docs:` - Documentación
- `chore:` - Tareas de mantenimiento

Ejemplo: `feat: añadir sección de testimonios`
