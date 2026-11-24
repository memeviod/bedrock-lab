# Bedrock Lab

**Bedrock Lab** is a lightweight discovery catalog for Minecraft Bedrock community content. It brings together search results and links to the original publications while keeping each creator's and platform's content attribution intact.

- **Website:** <https://bedrock-lab-memeviod.onrender.com/>
- **Repository:** <https://github.com/memeviod/bedrock-lab>
- **Android releases:** <https://github.com/memeviod/bedrock-lab/releases>
- **Issues:** <https://github.com/memeviod/bedrock-lab/issues>

## Content sources

Bedrock Lab currently integrates four external sources:

| Source | How the catalog uses it |
| --- | --- |
| [CurseForge](https://www.curseforge.com/minecraft-bedrock) | API search, available metadata, and eligible direct file downloads. Requires an API key. |
| [MCPEDL](https://mcpedl.com/) | Public catalog/API data and links to original publications. |
| [ModBay](https://modbay.org/) | Public catalog pages and links to original publications. |
| [McPack.cc](https://www.mcpack.cc/) | Public catalog pages when available; the app can fall back to a local index, whose capture date is shown. |

The availability of content, versions, download links, dates and statistics depends on the relevant source. Bedrock Lab does not guarantee compatibility or availability. Read the original publication before installing a pack.

## What the site includes

- Search, pagination, category/source/version filters, and sorting by the data currently available.
- A responsive catalog with item details and links back to original sources.
- A closing “Visita GitHub” section that describes the repository and links directly to the project.
- Locally stored favorites and recent items in the user's browser; no Bedrock Lab account is needed for these local lists.
- A Java-resource-pack conversion link operated by McPack.cc, and an installation guide.
- An Android app distributed through GitHub Releases.

Favorites and recent IDs are stored locally in the browser. They are not synchronized between devices or accounts. The catalog continues to use the current source integrations; no ranking or publication date is invented when a source does not provide one.

## Project layout

| Path | Purpose |
| --- | --- |
| `index.html` | Main web interface and client-side behavior. |
| `server.js` | Lightweight Node.js HTTP server, API integrations, cache, downloads, and static assets. |
| `package.json` | Start script and Node.js runtime declaration. |
| `manifest.json`, `icon-192.png`, `icon-512.png`, `brand.webp` | PWA metadata and project visuals. |
| `mcpack-index.json` | Local fallback index for McPack.cc when its live catalog cannot be reached. |
| `bedrock-lab-android-source.zip` | Android app source archive used by the repository's build workflow. |
| `.github/workflows/android-apk.yml` | Android GitHub Actions workflow. |

## Run locally

Requirements: Node.js 18 or later, Git, and a CurseForge API key for CurseForge results.

```sh
git clone https://github.com/memeviod/bedrock-lab.git
cd bedrock-lab
```

Set the environment variable `CURSEFORGE_API_KEY` in your local shell or deployment environment. Do not commit the key or paste it into public issues.

Linux/macOS:

```sh
export CURSEFORGE_API_KEY="YOUR_API_KEY"
npm start
```

Windows PowerShell:

```powershell
$env:CURSEFORGE_API_KEY="YOUR_API_KEY"
npm start
```

The server listens on the port provided by `PORT`, or port `3000` when `PORT` is not set. The configured `npm start` script runs `node server.js`.

## API routes

| Route | Purpose |
| --- | --- |
| `GET /api/search` | Search the configured catalog sources, with query, page and filter parameters. |
| `GET /api/details?id=...` | Request the detail data available for a catalog item. |
| `GET /api/download?mod=...&file=...` | Download an eligible CurseForge file; otherwise the source's publication page is used. |
| `GET /manifest.json` | Serve the web-app manifest. |

Source websites may be unavailable, change their pages, limit access, or provide incomplete metadata. The interface reports source failures where possible and continues with successful sources.

## Deployment, performance and security notes

- The app uses built-in Node.js APIs and does not require a heavy framework.
- Successful API responses use a short cache policy; CurseForge API and public catalog-page responses are also cached in memory by the server. The cache is instance-local and resets when the process restarts.
- Search remains paginated; images in the interface are lazy-loaded. The client debounces search input and aborts obsolete browser requests. The server also cancels upstream work when the client disconnects, applies upstream timeouts, bounds search pages and limits simultaneous API requests.
- The HTTP server sets content-type, framing, referrer and permissions headers. A strict Content Security Policy is not set because the current page includes inline code and displays images from external catalog providers; review before changing this architecture.
- Never put API keys, signing keys or passwords in the repository. Keep them in protected deployment secrets/environment settings.
- Do not change the external integrations, download flow, Render settings, or Android signing workflow without testing the effects.

## External content and attribution

Bedrock Lab is an aggregation and discovery interface; it does not claim ownership of third-party addons, maps, textures, skins, or other resources. Those remain the property of their respective creators and publishers. Consult original source pages for permissions, current downloads, updates, and compatibility.

## Contributing and reporting issues

Please report bugs or source integration changes through [GitHub Issues](https://github.com/memeviod/bedrock-lab/issues). Include the affected page/source and steps to reproduce, but never include API keys, passwords, private signing material, or personal tokens.

## Credits

Created by **MEMEVIOD**. Project developed with help from **Zapia**.
