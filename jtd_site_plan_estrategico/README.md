# Sitio Jekyll (Just the Docs) — Plan Estratégico Institucional

Este repositorio está listo para publicarse **gratis** en **GitHub Pages** usando el tema **Just the Docs**.

## Pasos de publicación

1. Crea un repositorio en GitHub (público o privado con Pages).
2. Sube el contenido de esta carpeta al repositorio.
3. Ve a **Settings → Pages** y en **Source** elige **GitHub Actions** o **Deploy from a branch** (main / root).
4. Si usas **GitHub Actions**, añade este workflow (opcional). Con *Deploy from a branch*, GitHub Pages compila Jekyll automáticamente.

### Workflow opcional (GitHub Actions)
Crea `.github/workflows/pages.yml` con:

```yaml
name: Deploy Jekyll with GitHub Pages
on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v5
      - uses: actions/jekyll-build-pages@v1
      - uses: actions/upload-pages-artifact@v3
        with:
          path: ./
      - uses: actions/deploy-pages@v4
```

## Estructura
```
/
  _config.yml
  index.md
  /docs
    *.md  # páginas por sección
```

## Notas
- Esta es una conversión automática. Revisa títulos, tablas y listas.
- Si prefieres **Astro + Starlight**, puedes copiar los `.md` dentro de `src/content/docs/` y usar su plantilla.