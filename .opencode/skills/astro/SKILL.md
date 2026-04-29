---
name: astro
description: Guía de Astro para componentes, layouts, patrones y optimización
license: MIT
compatibility: opencode
metadata:
  framework: astro
  version: 6.x
---

## Componentes Astro

### Estructura básica

```astro
---
// Script frontmatter (TypeScript)
interface Props {
  title: string;
  description?: string;
}

const { title, description = 'Valor por defecto' } = Astro.props;
---

<!-- Template HTML -->
<div class="component">
  <h1>{title}</h1>
  {description && <p>{description}</p>}
  <slot /> <!-- Contenido hijo -->
</div>

<style>
  /* Estilos scoped por defecto */
  .component { color: red; }
</style>
```

### Props

- Siempre definir `interface Props` en el frontmatter
- Usar destructuring con valores por defecto
- TypeScript estricto habilitado en este proyecto

### Slots

```astro
<!-- Slot por defecto -->
<slot />

<!-- Slot con fallback -->
<slot name="header">
  <p>Contenido por defecto</p>
</slot>

<!-- Uso -->
<Component>
  <p slot="header">Header personalizado</p>
  <p>Contenido default</p>
</Component>
```

## Layouts

```astro
---
// src/layouts/Layout.astro
interface Props {
  title: string;
  description?: string;
}

const { title, description } = Astro.props;
---

<!doctype html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content={description} />
    <title>{title}</title>
  </head>
  <body>
    <slot />
  </body>
</html>

<style is:global>
  /* Estilos globales - usar con precaución */
  @import '../styles/global.css';
</style>
```

## Estilos

### Scoped (por defecto)

```astro
<style>
  p { color: blue; } /* Solo aplica a este componente */
</style>
```

### Global

```astro
<style is:global>
  p { color: blue; } /* Aplica a toda la página */
</style>
```

### Variables CSS

```astro
---
const color = 'red';
---

<p style={`--color: ${color}`}>Texto</p>

<style>
  p { color: var(--color); }
</style>
```

## Directivas

### `class:list`

```astro
<div class:list={['base', { active: isActive }, 'extra']} />
```

### `set:html`

```astro
<div set:html={htmlContent} />
```

### `define:vars`

```astro
<style define:vars={{ color, size }}>
  p { color: var(--color); font-size: var(--size); }
</style>
```

## Fetching de datos

### En el frontmatter

```astro
---
// Se ejecuta en build/server
const response = await fetch('https://api.example.com/data');
const data = await response.json();
---

<div>{data.map(item => <p>{item.name}</p>)}</div>
```

### Archivos locales

```astro
---
import data from '../data/content.json';
---

<div>{data.items.map(item => <p>{item}</p>)}</div>
```

## Integraciones

### React (si está instalado)

```astro
---
import ReactComponent from '../components/React.jsx';
---

<ReactComponent client:load />
<!-- client:load | client:idle | client:visible | client:media -->
```

## Rutas

- `src/pages/index.astro` → `/`
- `src/pages/about.astro` → `/about`
- `src/pages/blog/[slug].astro` → `/blog/:slug` (rutas dinámicas)

## Optimización

### Imágenes

```astro
---
import { Image } from 'astro:assets';
import myImage from '../assets/image.png';
---

<Image src={myImage} alt="Descripción" />
```

### Meta tags

```astro
<head>
  <meta name="description" content={description} />
  <meta property="og:title" content={title} />
  <meta property="og:image" content={ogImage} />
  <link rel="canonical" href={canonicalUrl} />
</head>
```

## Comandos útiles

```bash
npm run dev          # Servidor desarrollo (localhost:4321)
npm run build        # Build producción
npm run preview      # Preview build local
npm run astro add   # Añadir integraciones
npm run astro check # Verificar tipos
```

## Patrones en este proyecto

- Layout principal: `src/layouts/Layout.astro`
- Componentes UI: `src/components/ui/` (Button, Card, SectionTitle)
- Componentes sección: `src/components/` (Header, Hero, Services, etc.)
- Animaciones scroll: clase `.reveal` + IntersectionObserver en Layout
- Estilos globales: `src/styles/global.css`
- Idioma: español (`lang="es"`)
