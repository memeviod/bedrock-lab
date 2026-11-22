# Bedrock Lab
🧱 Bedrock Lab

<p align="center">
  <img src="brand.webp" alt="Bedrock Lab Logo" width="160">
</p><h3 align="center">THE BEDROCK CONTENT HUB</h3><p align="center">
  <strong>Discover. Explore. Download.</strong>
  <br>
  Your Minecraft Bedrock content, brought together in one place.
</p><p align="center">
  <a href="https://github.com/memeviod/bedrock-lab/stargazers"><img src="https://img.shields.io/github/stars/memeviod/bedrock-lab?style=for-the-badge&color=8b5cf6" alt="Stars"></a>
  <a href="https://github.com/memeviod/bedrock-lab/network/members"><img src="https://img.shields.io/github/forks/memeviod/bedrock-lab?style=for-the-badge&color=6366f1" alt="Forks"></a>
  <a href="https://github.com/memeviod/bedrock-lab/releases"><img src="https://img.shields.io/github/v/release/memeviod/bedrock-lab?style=for-the-badge&color=7c3aed" alt="Latest Release"></a>
  <img src="https://img.shields.io/badge/Platform-Minecraft%20Bedrock-22c55e?style=for-the-badge" alt="Minecraft Bedrock">
</p><p align="center">
  <a href="https://bedrock-lab-memeviod.onrender.com/"><strong>🌐 VISIT WEBSITE</strong></a>
  &nbsp; • &nbsp;
  <a href="https://github.com/memeviod/bedrock-lab/releases"><strong>📦 DOWNLOAD</strong></a>
  &nbsp; • &nbsp;
  <a href="https://github.com/memeviod/bedrock-lab/issues"><strong>REPORT AN ISSUE</strong></a>
</p>---

01 — Overview

Bedrock Lab is a Minecraft Bedrock content aggregation project that brings together resources from multiple external platforms through a unified interface.

Its purpose is to simplify content discovery by providing a centralized place to explore different types of community-created resources without having to navigate each source independently.

Available through a web interface and an Android application, Bedrock Lab combines accessibility, organization and a dedicated experience for Minecraft Bedrock players.

02 — Content ecosystem

Bedrock Lab connects with several established Minecraft content platforms.

Source| Platform
"CurseForge" (https://www.curseforge.com/minecraft-bedrock)| Addons and content packs
"MCPEDL" (https://mcpedl.com/)| Addons, maps and textures
"ModBay" (https://modbay.org/)| Mods and community content
"McPack.cc" (https://mcpack.cc/)| Minecraft Bedrock packs

Content categories

- Addons: Extend Minecraft Bedrock with community-created content.
- Texture Packs: Discover visual modifications and resource packs.
- Maps: Explore custom worlds and environments.
- Skins: Find character appearances.
- Other resources: Additional content available through integrated sources.

Content availability, ownership and updates are determined by the respective external platforms and creators.

03 — Platforms

Web application

Access Bedrock Lab directly from your browser.

<p align="center">
  <a href="https://bedrock-lab-memeviod.onrender.com/">
    <strong>OPEN BEDROCK LAB →</strong>
  </a>
</p>Android application

The Android version provides access to the catalog through a dedicated mobile experience, including its own downloads section.

<p align="center">
  <a href="https://github.com/memeviod/bedrock-lab/releases">
    <strong>EXPLORE ANDROID RELEASES →</strong>
  </a>
</p>04 — Technology

The project uses a lightweight Node.js server architecture.

Component| Technology
Server runtime| Node.js
Minimum Node.js version| 18
Server entry point| "server.js"
Main web interface| "index.html"
Content integration| CurseForge API
Application metadata| JSON

05 — Installation & Development

Want to run your own local instance?

Requirements

- Node.js 18 or later.
- A valid CurseForge API key.
- Git.

Clone the repository

git clone https://github.com/memeviod/bedrock-lab.git
cd bedrock-lab

Configure the API key

Set the "CURSEFORGE_API_KEY" environment variable.

Linux / macOS:

export CURSEFORGE_API_KEY="YOUR_API_KEY"

Windows PowerShell:

$env:CURSEFORGE_API_KEY="YOUR_API_KEY"

Start the server

npm start

The server will start using the repository's configured start script.

Security notice: Never publish API keys, credentials or other private configuration values in the repository.

06 — External content & attribution

Bedrock Lab acts as an aggregation and discovery interface.

It does not claim ownership of third-party addons, maps, textures, skins or other resources displayed through its integrations.

All external content remains the property of its respective creators and publishers. Original sources should be consulted for downloads, permissions, updates and compatibility information.

07 — Releases

Bedrock Lab has publicly published releases containing project versions and associated files.

Explore the release history to find available versions and updates.

<p align="center">
  <a href="https://github.com/memeviod/bedrock-lab/releases">
    <strong>VIEW ALL RELEASES →</strong>
  </a>
</p>08 — Credits & Development

Bedrock Lab is a project created and directed by MEMEVIOD.

A special recognition goes to Zapia, which contributed more than 80% of the project's development work.

Its contribution was fundamental to the implementation and construction of the project.

Contributor| Contribution
MEMEVIOD| Project creator, direction and development
Zapia| Main development contribution — over 80% of the work

This project would not be what it is today without that contribution.

---

<p align="center">
  <img src="brand.webp" alt="Bedrock Lab" width="90">
  <br>
  <strong>BEDROCK LAB</strong>
  <br>
  <sub>A unified gateway to the Minecraft Bedrock content ecosystem.</sub>
  <br><br>
  Created by <a href="https://github.com/memeviod">MEMEVIOD</a>
</p>
**Creado por MEMEVIOD.** Proyecto desarrollado con ayuda de Zapia.

Catálogo de addons, texturas, mapas y otros contenidos para Minecraft Bedrock: CurseForge, MCPEDL, ModBay y McPack.cc. La app Android muestra este catálogo y añade su propia pestaña de descargas.

Para ejecutar el servidor, usa Node.js 18 o superior, configura la variable de entorno `CURSEFORGE_API_KEY` y ejecuta `npm start`. La clave se almacena como variable de entorno, nunca en el repositorio.

Las fichas y descargas enlazan a sus publicaciones originales cuando corresponde. Los contenidos pertenecen a sus respectivos creadores; comprueba la compatibilidad antes de instalar.
https://bedrock-lab-memeviod.onrender.com/