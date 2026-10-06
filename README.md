# Techno Plast — client pitch website

A responsive React + TypeScript website with an interactive Three.js powder-coating sample, shadcn/Radix controls, Motion scroll reveals, and real Instagram content.

## Run locally

```sh
npm install
npm run dev -- --port 5173
```

Open http://localhost:5173. The current workspace preview is already running on this port.

## Features

- A real WebGL sample with rounded metal geometry, a hanging hole, multiple layers, studio lighting and powder texture.
- Interruptible colour interpolation; matt, satin and gloss material settings; drag, keyboard, auto-rotation and reset controls.
- A searchable 12-shade library with colour-family filtering.
- Product/application detail dialogs and an email enquiry that includes the chosen shade and finish.
- Downloadable company catalogue and real Instagram post links with locally stored images.
- Desktop and mobile layouts, accessible dialogs, keyboard navigation, reduced-motion support and WebGL fallback.
- Local fonts and images. The 3D renderer is lazy-loaded and skips rendering while idle, offscreen or in a hidden tab.

## Checks

```sh
npm run build
npm run lint
npx playwright install chromium
npm run test:e2e
```

Run the dev server before browser tests. If Chromium is already installed at a custom path, set `PLAYWRIGHT_CHROMIUM_EXECUTABLE` to its executable. Tests cover colour/finish controls, pointer and keyboard rotation, reset, library search, enquiry data, product details, real post links, loaded images, mobile navigation, widths from 320–1440px, reduced motion and WebGL fallback.

`node scripts/capture.mjs` captures desktop/mobile design previews into `research/` while the server is running.

## Content and launch notes

See [CONTENT-SOURCES.md](CONTENT-SOURCES.md) for exact sources and research dates. Public Instagram posts were read on October 6, 2026, including the current phone number in the August 3 artwork. The email address comes from the existing company website.

The Instagram section is a static, curated snapshot. Automatic refresh requires the client's authorized Meta integration or an editorial CMS workflow. The sample form prepares an email for the visitor to send; it does not store or send submissions on a server. The colour preview is indicative, not a certified RAL match. Application photography is illustrative and labelled as such.

For production, confirm contact details with the client, connect their preferred enquiry delivery workflow if required, and deploy `dist/` to a static host. Nothing has been published to the company's existing domain.

## Main files

- `src/App.tsx` — page sections, dialogs and enquiry workflow.
- `src/App.css` — responsive design and motion styling.
- `src/components/PlateScene.tsx` — procedural 3D sample and interaction/render lifecycle.
- `src/data.ts` — colours, product descriptions and Instagram posts.
- `src/components/ui/` — shadcn components.
- `CONTENT-SOURCES.md` — source documentation.
- `tests/website.spec.ts` — functional browser checks.
# techno
