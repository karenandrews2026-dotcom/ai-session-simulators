# Karen's AI Session Simulators

Class diagrams and interactive pages for the course **AI, Your Way**. This folder is meant to be published with GitHub Pages so Karen can open every simulator from one home page.

Prepared for Karen. Please don't share.

## Open the site

Once Pages is on, the home page will be:

https://karenandrews2026-dotcom.github.io/ai-session-simulators/

## Turn on GitHub Pages

Karen does this in the repo settings (Nadeem will ask her; do not change settings from here):

1. Open **Settings > Pages**
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**
3. Set the branch to **main** and the folder to **/ (root)**
4. Save, then wait a minute or two for the site to go live

The repo can stay private only if the GitHub plan allows Pages on private repositories. If the site does not publish, the usual fix is to make the repository public (still do not share the pages themselves).

## What lives where

- `index.html` is the home page. It reads `simulators.json` and draws a card for each item. A static list of the same cards is also written into `index.html`, so the page still works if that file cannot be loaded.
- `simulators/` holds the actual files. A simulator can be an `.html`, `.svg`, `.png`, or `.pdf` file.
- `.nojekyll` tells GitHub Pages not to process the folder with Jekyll.

## Add a new simulator

1. Drop the file into `simulators/`. Keep it self-contained when you can (inline CSS and JS). If it needs extra images or assets, put them next to it (or in a subfolder) and use relative paths.
2. Add one object to the array in `simulators.json`:

```json
{
  "file": "your-file.html",
  "title": "Short title",
  "description": "One or two plain sentences.",
  "session": "7",
  "type": "html",
  "added": "2026-12-01"
}
```

`file` is the path under `simulators/`. `type` must be one of `html`, `svg`, `png`, or `pdf`. `session` is the class number.

3. Add a matching card to the fallback list inside `index.html` (the cards already in the `#grid` element). That way the home page still shows the new item if `simulators.json` fails to load. Copy an existing card and change the link, title, description, session, type, and date.

4. Commit and push to `main`. After Pages is on, the new card appears on the home page.

Do not put Session notes PDFs or working files here unless they are meant to be a simulator on the home page.
