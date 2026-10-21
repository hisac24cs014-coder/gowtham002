# Ultron AI

Your own AI chat website with two brains:

- **A: Claude API**: best quality, needs an API key and pay-per-use.
- **B: Open-source model (Ollama)**: free to run on your own computer, quality depends on your hardware.

You can switch between A and B from the menu on the website.

## Languages

Ultron AI detects the language of each message automatically (including mixed and romanized text) and replies in the same language. A menu with 132 languages lets you force a reply language. Claude (Brain A) handles most of them well; open-source models (Brain B) handle fewer languages and with lower quality, so expect weaker results for rare languages there.

## Setup

1. Install Node.js 18 or newer.
2. In this folder run `npm install`.
3. Copy `.env.example` to `.env`.
   - For A: put your `ANTHROPIC_API_KEY` (from https://console.anthropic.com).
   - For B: install Ollama from https://ollama.com, then run `ollama pull llama3.1` and `ollama serve`.
4. Run `npm start` and open http://localhost:3000

## Adding your own data

Click "Add data" on the website, or drop `.txt` / `.md` files into the `knowledge/` folder.
Before each answer, the server picks the most relevant paragraphs and gives them to the brain.

## Files

- `server.js`: backend, knowledge search, both brains
- `public/index.html`: the chat page
- `knowledge/`: your notes
- `.env.example`: settings template

## Limits (honest)

- This is not a copy of Claude. It uses Claude through the API (A) or a different open model (B).
- It does not store "all world data". It knows what the brain model knows plus the notes you add.
- Knowledge search is simple keyword matching. For big document sets, upgrade to embeddings and a vector database.
- Never put your API key in the web page or share your `.env` file.
