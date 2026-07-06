# Repo Favicons

Internal asset library for the DaveHomeAssist estate: one canonical SVG favicon per project/repo in the ecosystem, plus a static gallery page for browsing and picking icons at a glance.

## What's in here

- **One SVG per project**, named to match the project's repo (e.g. `DaveHomeAssist.svg`, `DaveLLM.svg`, `NotionWidgets.svg`, `garden-os.svg`, `prompt-lab.svg`, `curl-plan.svg`, etc.). These SVGs are the source of truth for that project's icon.
- **`index.html`** — a static gallery page that renders every SVG in a grid via a hardcoded JS array (`{ file, name }` entries), so it's easy to eyeball the whole set and compare styles/colors across projects.
- **`favicon-preview.html`** — a thin redirect page (sets its own favicon, then immediately forwards to `index.html`). Effectively an alternate/legacy entry point into the same gallery.
- **`favicon.svg`** — this repo's own favicon, used by the two HTML pages above.
- **`AGENTS.md`** — agent-facing project notes (stack, key decisions, session log).
- No build step, no bundler, no dependencies — just static SVG + HTML.

## How new favicons get added

1. Author or export a new SVG for the project, and drop it in the repo root, named to match that project's repo (this is a manual/hand-authored step — there's no generator script in this repo).
2. Add a corresponding `{ file: "your-project.svg", name: "your-project" }` entry to the array in `index.html` so it shows up in the gallery.
3. Preview locally by opening `index.html` (or `favicon-preview.html`, which just redirects there) in a browser — no server or build required.
4. Commit the new SVG (and the `index.html` array update) to `main`.

Per `AGENTS.md`, this repo holds the canonical SVG sources; any PNG favicon sets (favicon-16/32.png, apple-touch-icon.png, etc.) that a project needs are derived from the SVG here, not the other way around.

## How other repos consume these icons

There's no runtime linking (no repo fetches an SVG from this repo's raw GitHub URL at page-load time). Instead, the SVG is **copied verbatim** into the consuming project's own favicon/icon assets folder. For example, `NotionWidgets/assets/icons/favicon/favicon.svg` in the `NotionWidgets` repo is byte-identical to `NotionWidgets.svg` here — confirming the workflow is "copy the canonical source into the project, then regenerate any PNG sizes from it locally."

This repo itself is also listed as a project entry on the estate's hub dashboard (`DaveHomeAssist.github.io`), described there as "Shared favicon and icon assets for all repos," and is published via GitHub Pages at `davehomeassist.github.io/repo-favicons` so the gallery is browsable online as well as locally.
