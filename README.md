# Karen's AI Session Simulators

Class diagrams and interactive pages for the course **AI, Your Way**. This folder is published with GitHub Pages so every simulator can be opened from one home page.

Prepared for Karen. Please don't share.

## Open the site

The home page is:

https://karenandrews2026-dotcom.github.io/ai-session-simulators/

The repo is public so GitHub Pages can host it. Pages is set to Deploy from a branch, `main`, folder `/ (root)`. Do not put personal data here (no emails, health or private work details).

If Pages ever needs to be set again:

1. Open **Settings > Pages**
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**
3. Set the branch to **main** and the folder to **/ (root)**
4. Save, then wait a minute or two for the site to go live

## What lives where

- `index.html` is the home page. It reads `simulators.json` and draws a card for each item. A static list of the same cards is also written into `index.html`, so the page still works if that file cannot be loaded.
- `simulators/` holds the actual files. A simulator can be an `.html`, `.svg`, `.png`, or `.pdf` file.
- `.nojekyll` tells GitHub Pages not to process the folder with Jekyll.

These pages are concept resources. They are not tied to a class number.

## Add a new simulator

1. Drop the file into `simulators/`. Keep it self-contained when you can (inline CSS and JS). If it needs extra images or assets, put them next to it (or in a subfolder) and use relative paths.
2. Add one object to the array in `simulators.json`:

```json
{
  "file": "your-file.html",
  "title": "Short title",
  "description": "One or two plain sentences.",
  "type": "html",
  "added": "2026-12-01"
}
```

`file` is the path under `simulators/`. `type` must be one of `html`, `svg`, `png`, or `pdf`.

3. Add a matching card to the fallback list inside `index.html` (the cards already in the `#grid` element). That way the home page still shows the new item if `simulators.json` fails to load. Copy an existing card and change the link, title, description, type, and date.

4. Commit and push to `main`. After Pages has rebuilt, the new card appears on the home page.

Do not put class notes PDFs or working files here unless they are meant to be a simulator on the home page.
