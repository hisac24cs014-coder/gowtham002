# Ultron AI — Online Deployment Package

## Publish on Render

1. Extract this ZIP.
2. Create a repository on GitHub.
3. Upload the **contents of this folder** (including `render.yaml`, `server.js`, `package.json`, `public/`, and `knowledge/`) to the repository root.
4. Sign in at https://render.com and choose **New → Blueprint**.
5. Connect your GitHub repository and deploy the Blueprint.
6. In Render's service environment settings, set `ANTHROPIC_API_KEY` to your Anthropic API key from https://console.anthropic.com. Keep it secret; never put it in frontend code or commit it to GitHub.
7. After deployment finishes, open the public `onrender.com` URL Render provides.

## Important
- This package prepares deployment; it does not itself create a hosted URL.
- AI replies need a valid Anthropic API key and may incur API charges.
- A free hosting service may sleep when inactive and take time to wake.
- `OLLAMA_URL=http://localhost:11434` is for local development only. A cloud host cannot reach Ollama running on your own computer; use Claude or configure a separately hosted Ollama endpoint.
- Files uploaded to a free instance may not persist across redeploys/restarts. Keep important knowledge files in the repository or configure persistent storage.
- Never publish your `.env` file or API key.
