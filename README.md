# Beezos Web OS

Responsive Next.js web desktop with custom bee mascot, Shift Browser launch/search panel, dock, Notes, sample Files, wallpaper settings, AI API, and protected owner console.

## Local development
- Node.js 20+
- `npm install`
- Copy `.env.example` to `.env.local` and set desired credentials
- `npm run dev`

## Environment
- `OWNER_PASSWORD` and `SESSION_SECRET` enable signed HttpOnly owner sessions.
- `KV_REST_API_URL` and `KV_REST_API_TOKEN` enable persistent maintenance settings using Vercel KV. Without these, the app explicitly reports that persistence is not configured.
- `OPENAI_API_KEY` enables the server-side assistant. Optional `OPENAI_MODEL` defaults to `gpt-4o-mini`.

Set secrets in Vercel Project Settings → Environment Variables; never put secrets in client code or commit them. Add provider-side usage limits and production rate limiting before opening the AI endpoint to high traffic.

Shift opens the official https://shift.com site. This web app is not a browser engine, privileged hardware scanner, or cloud file provider. Notes and wallpaper preferences are local to the browser; Files are demo items.

## Deploy
Import this repo into Vercel as a Next.js project, add the environment variables, and connect a KV store for persistent owner settings.