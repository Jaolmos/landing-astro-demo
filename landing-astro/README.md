# NovaTech Studio - Landing Page

Landing page construida con Astro para NovaTech Studio.

## Estructura del Proyecto

```text
/
├── public/                  # Assets estáticos (favicon)
├── src/
│   ├── components/          # Componentes de sección
│   ├── components/ui/       # UI reutilizable (Button, Card, SectionTitle)
│   ├── layouts/             # Layout raíz
│   ├── pages/               # Páginas (index.astro)
│   └── styles/              # Estilos globales
└── package.json
```

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
