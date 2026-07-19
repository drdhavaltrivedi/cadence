# Deploying Cadence

Cadence is a single static file (`index.html`). No build step, no server, no dependencies.

## Fastest: GitHub Pages (this repo)

1. Repo Settings → Pages → Source: **Deploy from a branch**.
2. Branch: `main`, folder: `/ (root)` → Save.
3. Site goes live at `https://drdhavaltrivedi.github.io/cadence/` within a minute or two.

## Alternative: Netlify / Cloudflare Pages

Drag-and-drop the repo folder (or connect this GitHub repo). No build command, publish directory = repo root. Both free tiers are more than enough.

## Custom domain later

Add a CNAME in your DNS pointing at the host, then set the custom domain in the host's dashboard. Update the `og:url` meta tag in `index.html` to match.

## Requirements for the mic to work

- Must be served over **HTTPS** (or `localhost`). `getUserMedia` is blocked on plain HTTP. All hosts above serve HTTPS by default.
- Test recording on a real iPhone (Safari) and a real Android (Chrome) before sharing widely — Safari's MediaRecorder produces `audio/mp4`, Chrome produces `webm`; the code handles both, but device behavior should be verified by hand.

## Progress storage

Progress (streaks, completed drills, theme) is stored in the browser's `localStorage` under the `cadence-state` key. Clearing site data resets it. There is no account or server — nothing to operate.
