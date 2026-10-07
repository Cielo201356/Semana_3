# Auditoría del proyecto Semana_3

**Fecha:** 7 de octubre de 2026  
**Repositorio:** [Cielo201356/Semana_3](https://github.com/Cielo201356/Semana_3)  
**Rama publicada:** `main`  
**Estado:** despliegue en GitHub Pages verificado

## Alcance

Este informe registra la preparación del repositorio, la configuración de GitHub Actions, la publicación del sitio estático y las verificaciones realizadas. La carpeta de trabajo contiene la página `index.html` y su hoja de estilos `styles.css`.

## Trabajo realizado

1. Se inicializó el repositorio Git local en la rama `main` y se conectó al remoto `https://github.com/Cielo201356/Semana_3.git`.
2. Se subieron el sitio existente y el workflow de publicación a GitHub.
3. Se creó `.github/workflows/deploy.yml` para publicar el contenido del repositorio en GitHub Pages:
   - Ejecuta con cada `push` a `main` o mediante `workflow_dispatch`.
   - Concede los permisos `contents: read`, `pages: write` e `id-token: write`.
   - Usa `actions/configure-pages`, `actions/upload-pages-artifact` y `actions/deploy-pages`.
   - Configura el entorno `github-pages` y evita despliegues concurrentes con `cancel-in-progress`.
4. Se verificó que GitHub Actions reconociera el workflow.
5. Se realizaron tres ejecuciones de despliegue:
   - **Ejecución 1:** falló porque Pages aún no estaba habilitado para el repositorio.
   - **Ejecución 2:** intentó habilitar Pages desde el workflow; GitHub rechazó la operación porque el token automático no tenía permiso para crear el sitio de Pages.
   - **Ejecución 3:** tras habilitar Pages en el repositorio, se quitó ese intento de habilitación automática y el despliegue terminó correctamente.
6. Se abrió el sitio publicado y se confirmó que aparecen el encabezado y las tres tarjetas de servicios.
7. Se añadió este informe de auditoría como `auditor.md`.

## Historial de cambios

| Commit | Descripción |
|---|---|
| `3dbc76c` | Inicialización del repositorio y configuración inicial de GitHub Pages. |
| `20b9d28` | Intento de habilitar Pages desde el workflow. |
| `88736f5` | Reintento del despliegue con Pages habilitado. |

El contenido de la página y los estilos existentes se conservaron; no se requirieron cambios funcionales en `index.html` ni en `styles.css`.

## Resultado y evidencias

- **Sitio publicado:** [https://cielo201356.github.io/Semana_3/](https://cielo201356.github.io/Semana_3/)
- **Ejecución exitosa de GitHub Actions:** [ejecución 3](https://github.com/Cielo201356/Semana_3/actions/runs/37695118581)
- **Workflow:** [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)
- La rama local `main` estaba sincronizada con `origin/main` al finalizar la publicación.

## Recomendaciones

1. Mantener GitHub Pages configurado para desplegar mediante **GitHub Actions**.
2. Revisar la pestaña **Actions** después de cambios relevantes y confirmar que la ejecución concluya en `success`.
3. Probar la página publicada tras cada cambio visual para verificar que los recursos carguen correctamente.
4. Si se desea publicar también en un servicio distinto de GitHub Pages, identificar ese servicio y configurar un flujo de despliegue independiente. La dirección denominada “GitParcher” durante la solicitud correspondía al mismo repositorio de GitHub; no se proporcionó otro destino.

## Conclusión

El sitio estático quedó publicado en GitHub Pages y la última ejecución de GitHub Actions finalizó correctamente. La publicación se verificó visualmente en la URL del sitio. Los dos primeros intentos fallidos se debieron a que Pages no estaba habilitado y a que el token de Actions no podía habilitarlo por sí solo; una vez habilitado Pages en el repositorio, el flujo configurado completó el despliegue.
