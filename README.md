# Semana 3 — Galería de servicios

Sitio web estático en español que presenta los servicios de una empresa en una galería adaptable a distintos tamaños de pantalla.

## Sitio publicado

Visita la página en [GitHub Pages](https://cielo201356.github.io/Semana_3/).

## Contenido

La página muestra tres servicios:

- **Desarrollo Web:** sitios rápidos, accesibles y responsivos.
- **Diseño UI/UX:** interfaces claras centradas en el usuario.
- **Seguridad:** buenas prácticas para proteger los datos.

El diseño se adapta a pantallas pequeñas y grandes, e incluye estilos para la preferencia de tema oscuro del sistema.

## Estructura del proyecto

```text
Semana_3/
├── index.html
├── styles.css
├── auditor.md
└── .github/
    └── workflows/
        └── deploy.yml
```

- `index.html`: estructura y contenido de la página.
- `styles.css`: presentación, diseño responsivo y tema oscuro.
- `auditor.md`: registro de los cambios y verificaciones del despliegue.
- `.github/workflows/deploy.yml`: publicación automática en GitHub Pages.

## Uso local

No se requiere instalar dependencias ni compilar el proyecto. Clona el repositorio y abre `index.html` en un navegador:

```bash
git clone https://github.com/Cielo201356/Semana_3.git
cd Semana_3
```

También puedes iniciar un servidor estático local desde la carpeta del proyecto, por ejemplo:

```bash
python -m http.server 8000
```

Después visita [http://localhost:8000](http://localhost:8000).

## Despliegue

GitHub Actions publica el contenido del repositorio en GitHub Pages:

- Automáticamente al hacer `push` a la rama `main`.
- Manualmente desde **Actions → Deploy static site to GitHub Pages → Run workflow**.

El repositorio debe tener GitHub Pages configurado para desplegar con **GitHub Actions**. El workflow y sus permisos están definidos en [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).

## Auditoría

Consulta [`auditor.md`](auditor.md) para ver el historial de publicación, los resultados de las ejecuciones y las recomendaciones.
