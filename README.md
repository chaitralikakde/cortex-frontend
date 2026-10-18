# Cortex frontend

Next.js desk for Cortex. The browser talks only to this app. `/api/*` is rewritten to the FastAPI backend, so FalkorDB credentials never reach the browser.

## Run locally (with Docker API)

1. In the main Cortex repo, start FalkorDB and the API:

```bash
docker compose up -d falkordb api
```

2. In this folder:

```bash
npm ci
npm run dev
```

3. Open http://localhost:3000

The rewrite uses `API_URL` (default `http://localhost:8000`).

```bash
# PowerShell
$env:API_URL="http://localhost:8000"; npm run dev
```

## Run the full stack with Docker

From the **main** Cortex repo (not this folder):

```bash
docker compose up -d --build
```

Then open http://localhost:8080

## Deploy on Vercel

1. Import [chaitralikakde/cortex-frontend](https://github.com/chaitralikakde/cortex-frontend) in Vercel.
2. Framework: **Next.js**. Root: `.`
3. Environment variable:
   - `API_URL` = public URL of the Cortex API, no trailing slash  
     Example: `https://cortex-api.example.com`
4. Deploy.

The API must already be live and reachable from Vercel. CORS on the API already allows all origins. Slack, GitHub, and other tokens stay on the API, not on Vercel.

## Scripts

```bash
npm run dev      # local
npm run build    # production build
npm run start    # serve the build
```
