# aplisay — consultative transfer poll

A single static page that plays an audio clip and asks visitors to choose one of
two approaches to AI agent consultative transfers, with a live shared vote count.

## Files
- `index.html` — the page (all HTML/CSS/JS inline)
- `transfer-demo.wav` — the audio clip played on the page
- `netlify.toml` — Netlify config (no build, publish root)

## How the live count works
Shared counts use the free [Abacus](https://abacus.jasoncameron.dev) counter API.
No backend or signup needed. The poll lives under the namespace set in `CONFIG.namespace`
inside `index.html` — change it to start a fresh tally.

Counter keys must be longer than one character, so the two options are stored as
`option_a` / `option_b`.

## Deploy (Netlify)
This is a static site — point Netlify at the repo root with no build command.
The page must be served over http(s) (Netlify does this); opening `index.html`
directly from disk (`file://`) will block the counter and audio fetches.

## Config
Editable constants are at the top of the `<script>` block in `index.html`:
title, body text, the two option labels, audio path, namespace, refresh interval,
and one-vote-per-browser toggle.
