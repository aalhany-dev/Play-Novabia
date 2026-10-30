# Play Novabia — Godot Browser/PWA Development Build

**Live playable prototype:** https://play.novabia.dev/  
**Repository:** https://github.com/aalhany-dev/Play-Novabia  
**Audience:** Players, playtesters, collaborators and investors who wish to experience the existing **development build**.

This is a **pre-release, pre-revenue playable development prototype**, not the finished commercial game. Features, art, gameplay, availability and performance can change between builds.

## Domain and responsibility boundaries

- **https://novabia.dev/** — official marketing site and game information; owned by `aalhany-dev/Novabia`.
- **https://play.novabia.dev/** — exported Godot web application/PWA; owned by **this repository**.
- **https://eip.novabia.dev/** — investment and economic information; owned by `aalhany-dev/EIP-Novabia`.

**Public support:** `support@novabia.dev`.  
**Investor inquiries:** `invest.in@novabia.dev`, via https://eip.novabia.dev/investors/.

## File responsibilities

This repository is primarily a **published Godot web export**. Many files are machine-generated and should be updated as one coordinated export rather than manually rewritten.

- `index.html`: exported HTML bootstrap; contains the canonical URL and basic descriptive metadata. Some of its content may be overwritten by future Godot exports—reapply metadata after re-export if necessary.
- `index.js`, `index.wasm`, `index.pck`: JS runtime, WebAssembly and packed game assets. Do not hand-edit.
- `index.service.worker.js`, `index.manifest.json`, offline and icon assets: PWA/service-worker support. Refresh together with each compatible export, and test cache invalidation after updates.
- `index.audio.*.js` worklets: audio support; do not hand-edit.
- `CNAME`: GitHub Pages custom domain `play.novabia.dev`.
- `robots.txt`: crawler instructions for the playable host.
- `sitemap.xml`: only the public app entry URL on this host.
- `README.md`: release, publishing, QA and cross-repository responsibilities.

## Publishing procedure

1. Export the approved build for web from the Godot source project.
2. Confirm that runtime resources (`.pck`, `.wasm`, JS, service workers, manifest and icons) correspond to the same export.
3. Review and preserve the final HTML title, meta description and `https://play.novabia.dev/` canonical tag.
4. Confirm `CNAME`, `robots.txt` and `sitemap.xml` remain intact; a Godot export may overwrite root files.
5. Test on desktop and mobile browsers, including first load, refresh, offline/PWA state where supported, audio, keyboard/mouse inputs, graphics, save/session behavior and cold-cache/hard-refresh updates.
6. Check game and privacy/terms links from the main site, and confirm that the build does not silently initiate unexpected downloads.
7. Keep a recoverable previous release branch before deploying a breaking export.

GitHub Pages deploys from the configured branch; verify the live deployment rather than assuming a commit has already propagated.

## Search and QR behavior

This host contains the playable application, **not** the main marketing content. The main site now has independently searchable URLs for World, Origins, Gameplay, Companions, Sound, Playtest, Feedback and Follow.

Keep:
- https://play.novabia.dev/ — the one QR destination for launching the build.
- https://play.novabia.dev/sitemap.xml — host-specific sitemap with the canonical entry URL.
- https://play.novabia.dev/robots.txt — discovery metadata.

Submit the Play sitemap separately within a verified Search Console Domain Property if you want the playable entry indexed. An exported canvas/WebAssembly application is not equivalent to a text-rich marketing page; most SEO discoverability should come from `novabia.dev`.

## Integrity, compliance and communications

- Never invent playtest statistics, sales, wishlists, retention metrics, release dates or completion status.
- Publicly distinguish this development prototype from a commercially released Steam build.
- Maintain appropriate asset use rights, AI-related content disclosures and store compliance before commercialization.
- Preserve privacy/terms links and ensure feedback collection follows the published disclosures.
- Feature changes, save compatibility and technical release notes should be recorded alongside production build updates.

**Backup:** `backup/pre-site-discovery-docs-2026-10-30` preserves the state before search-discovery additions.

© 2026 Novabia. All rights reserved.
