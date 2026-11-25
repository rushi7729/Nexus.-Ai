# NEXUS.AI starter

A small mobile-friendly chat website with a Netlify Function proxy. The browser never receives the AI provider API key.

## Project files

- `index.html` — website interface
- `netlify/functions/chat.mjs` — secure server-side AI request
- `netlify.toml` — Netlify configuration

## Deploy

1. Create a GitHub repository for this project and upload these files, keeping the folder structure.
2. In Netlify, choose **Add new project** → **Import an existing project**.
3. Connect the GitHub repository.
4. Leave the build command empty and set the publish directory to `.`.
5. Deploy the site.

## Connect an AI provider later

In Netlify site settings, open Environment variables and add:

- `NEXUS_API_URL` — the provider's OpenAI-compatible chat completions URL
- `NEXUS_API_KEY` — your private API key
- `NEXUS_MODEL` — the exact model identifier supplied by the provider

Then redeploy the site. Never put the API key in `index.html`, GitHub, or a public message.

The provider must support the OpenAI-compatible `/chat/completions` request format. Free inference availability and limits vary. A 20B model generally needs dedicated server-side compute and is not run by Netlify itself.

## Local preview

Open `index.html` in a browser to preview the interface. The AI chat will only work after deployment and provider configuration.
