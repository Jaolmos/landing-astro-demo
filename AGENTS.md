# AGENTS.md

## Resumen del Proyecto

Landing page de una sola página con Astro para "NovaTech Studio" (contenido en español). Todo el código fuente está en el subdirectorio `landing-astro/`.

## Datos Clave

- **Framework**: Astro v6.1.10, TypeScript (modo estricto)
- **Node**: Se requiere >=22.12.0
- **No hay tests, linting, CI ni pre-commit hooks** - no buscar
- **Idioma**: Todo el contenido visible está en español (`lang="es"`)

## Comandos

Ejecutar desde el directorio `landing-astro/`:

```bash
npm install          # Instalar dependencias
npm run dev          # Servidor de desarrollo en localhost:4321
npm run build        # Compilar a ./dist/
npm run preview      # Vista previa del build de producción
```

## Arquitectura

```
landing-astro/
├── src/
│   ├── pages/index.astro        # Página principal (única)
│   ├── layouts/Layout.astro     # Layout raíz (incluye JS de scroll reveal)
│   ├── components/              # Componentes de sección (Header, Hero, Services, etc.)
│   ├── components/ui/           # UI reutilizable (Button, Card, SectionTitle)
│   └── styles/global.css        # Estilos globales
└── public/                      # Assets estáticos (favicon)
```

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
