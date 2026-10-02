# Motion Gallery

A small gallery of motion design animations (each one is a single HTML file) made with Claude.
One `index.html` lists them all, with live previews, search, and a full-screen viewer.

## Folder structure

```
motion-gallery/
├── index.html          <- the gallery (edit the ANIMATIONS array here)
├── animations/
│   ├── 1.html          <- one self-contained animation per file
│   ├── 2.html
│   └── 3.html
└── README.md
```

## Add a new animation

1. Save the new file in `animations/`, for example `animations/4.html`.
2. Open `index.html` and add one line to the `ANIMATIONS` array near the top of the script:

```js
{ title: 'My New One', file: 'animations/4.html', description: 'What it shows.', tags: ['svg', 'loop'] },
```

3. Save and refresh. The card, preview, search and full-screen viewer all update from that one line.

Fields: `title` and `file` are required. `description`, `tags`, and the design size
`w` / `h` (default 1280 x 720) are optional. For a vertical video use `w: 1080, h: 1920`
so the preview is scaled and centred correctly.

## Viewer shortcuts

- Click a card to watch it full screen. Arrow keys switch animation, Esc closes.
- Every animation has a share link: `index.html#2` opens the second one directly.
- Middle-click or Ctrl/Cmd-click a card to open the raw file in a new tab.

## Run it

Open `index.html` in a browser. The list lives inside `index.html` itself (not a separate
JSON file) so it also works when you double-click the file, with no server needed.
If you later move the list into `animations.json`, you will need a server or GitHub Pages
because browsers block `fetch()` on `file://` pages.

## Publish on GitHub Pages

1. Push the folder to a GitHub repo.
2. Repo Settings > Pages > Source: "Deploy from a branch", choose `main` and `/ (root)`.
3. Your gallery appears at `https://<username>.github.io/<repo>/`.

## Tips for animation files

- Keep each file self-contained (inline CSS and JS) so it works as a card preview and on its own.
- Use `vmin` / `%` units and `100%` height so it fits any size, from a card thumbnail to a phone screen.
- Previews only run while on screen, so many animations will not slow a phone down.

## License

Add a `LICENSE` file (MIT is a good default for the code). Fonts loaded from Google Fonts are
under the SIL Open Font License.
