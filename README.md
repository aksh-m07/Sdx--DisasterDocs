# DisasterDoc

In-browser emergency guidance: **Nia** retrieves protocol-style excerpts, **Groq** turns them and your description into clear steps. Use **voice or text**, find **nearby hospitals**, **read responses aloud**, and use **follow-up chat**—one HTML page, nothing to install.

## Features

- **Retrieval + generation** — Optional [Nia](https://trynia.ai/) search (package + web-style) feeds snippets into the prompt; [Groq](https://groq.com/) generates streaming protocol-style guidance.
- **Voice** — Speech-to-text (Web Speech API) and read-aloud (speech synthesis).
- **Hospitals** — Geolocation + OpenStreetMap (Overpass) + Photon, with links to Google Maps.
- **Follow-up chat** — Ask more about the same scenario after you get a protocol (requires Groq).
- **History & settings** — Stored locally in your browser (`localStorage`).

## Quick start

1. Open **`DisasterDocs.html`** in a browser, **or** serve the folder so `index.html` redirects to the app:

   ```bash
   cd /path/to/SDX
   python3 -m http.server 8080
   ```

   Then visit `http://localhost:8080/`.

2. Open **Settings** and add your **Groq API key** (free tier at [console.groq.com](https://console.groq.com)). Optional: **Nia API key** for protocol retrieval before the model runs.

**Note:** Geolocation and some APIs work best over **HTTPS** or **`http://localhost`**. Opening the file as `file://` may block location or other features.

## Configuration

| Setting | Purpose |
|--------|---------|
| **Groq API key** | Required for main protocol generation and follow-up chat. |
| **Groq model** | Choose smaller (8B) or larger (70B) model in Settings. |
| **Nia API key** | Optional; enables Nia search before Groq. Without it, answers come from Groq only. |
| **Language / voice speed / text size** | Stored locally; adjust in Settings. |

Keys are saved in **browser local storage** only—treat them like passwords.

## Project layout

| File | Role |
|------|------|
| `DisasterDocs.html` | Full app (CSS + JS inline). |
| `index.html` | Redirects to `DisasterDocs.html` for simple local servers. |

## Tech stack

Vanilla HTML/CSS/JS (no build step). External services: Groq (OpenAI-compatible chat API), Nia (`apigcp.trynia.ai`), Overpass, Photon, browser speech and geolocation APIs.

## Disclaimer

DisasterDoc is a **software demo** for education and preparedness. It is **not** a substitute for professional emergency services, medical care, or official incident instructions. **Call your local emergency number** when life or safety is at risk. Do not rely on AI output in place of trained responders.

## License

Add a license file if you distribute this repository (e.g. MIT).
