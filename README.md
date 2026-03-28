# 2048 Smooth

Juego 2048 en HTML, CSS y JavaScript con:

- animaciones suaves con easing,
- efectos especiales temporales para fichas altas,
- sonido generado con Web Audio,
- selector de tamano de tablero.

## Publicacion en GitHub Pages

1. Crea un repositorio nuevo en GitHub.
2. Sube el contenido de esta carpeta a la rama `main`.
3. En GitHub, entra en `Settings > Pages`.
4. En `Build and deployment`, selecciona `GitHub Actions`.
5. Haz push a `main`.

El workflow `.github/workflows/deploy-pages.yml` desplegara la web automaticamente en GitHub Pages.

## Records globales con Cloudflare Worker

1. Instala dependencias:
   `npm install`
2. Autentica Wrangler:
   `npx wrangler login`
3. Crea estos secretos en Cloudflare:
   `npx wrangler secret put GITHUB_TOKEN`
   `npx wrangler secret put GITHUB_OWNER`
   `npx wrangler secret put GITHUB_REPO`
   `npx wrangler secret put GITHUB_LABEL`
   `npx wrangler secret put ALLOWED_ORIGIN`
4. Despliega el worker:
   `npx wrangler deploy`
5. Copia la URL del worker y pegala en `script.js` en `WORKER_API_URL`.

Worker desplegado actualmente:
`https://angeloso-2048-records.mcdrer.workers.dev`
