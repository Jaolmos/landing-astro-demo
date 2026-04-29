# NovaTech Studio - Landing Page

Landing page de demostración construida con Astro, HTML y CSS. Incluye SEO optimizado, structured data y componentes modulares.

## Características

- **SEO optimizado**: Meta tags (Open Graph, Twitter Cards), canonical URL, robots.txt, sitemap.xml
- **Structured data**: JSON-LD para Organization, WebSite y FAQPage
- **Componentes modulares**: Secciones independientes (Hero, Servicios, FAQ, etc.)
- **Responsive**: Diseño adaptable a todos los dispositivos
- **Animaciones**: Scroll reveal con IntersectionObserver

## Estructura del Proyecto

```text
/
├── public/
│   ├── favicon.svg          # Favicon
│   ├── robots.txt           # Directivas para crawlers
│   └── sitemap.xml          # Sitemap XML
├── src/
│   ├── components/          # Componentes de sección (Header, Hero, Services, etc.)
│   ├── components/ui/       # UI reutilizable (Button, Card, SectionTitle)
│   ├── layouts/             # Layout raíz (meta tags SEO, structured data)
│   ├── pages/               # Páginas (index.astro)
│   └── styles/              # Estilos globales
└── package.json
```

## Secciones de la Landing

Hero | Servicios | Nosotros | Portafolio | Testimonios | FAQ | Contacto

## Comandos

Todos los comandos se ejecutan desde la raíz del proyecto (`landing-astro/`):

| Comando                   | Acción                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Instalar dependencias                            |
| `npm run dev`             | Servidor de desarrollo en `localhost:4321`       |
| `npm run build`           | Compilar el sitio a `./dist/`                    |
| `npm run preview`         | Vista previa del build de producción             |
| `npm run astro ...`       | Ejecutar comandos CLI de Astro                   |
| `npm run astro -- --help` | Ayuda del CLI de Astro                           |

## Más información

- [Documentación de Astro](https://docs.astro.build)
- [Discord de Astro](https://astro.build/chat)
