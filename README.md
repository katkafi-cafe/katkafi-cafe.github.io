# Katkafi — 3D cat café website (concept demo)

An explorable 3D cat café for **Katkafi**: rescue, care, coffee and matchmaking for cats in Tunis.
Visitors enter through a welcome screen, drag to look around the café, tap hotspots to open
sections, and tap cats to make them meow.

Live site: https://katkafi-cafe.github.io/ (GitHub Pages, updates on every push to `main`)

## Run it locally

The page loads images, so it needs a small local web server (opening `index.html` directly
from disk won't show the characters and pictures).

```bash
cd orbit-room-demo
python -m http.server 8000
```

Then open http://localhost:8000 in a browser. Any static server works (`npx serve`, VS Code Live Server, …).

There is no build step: everything is in `index.html`, and Three.js and the fonts load from CDNs.

## Where things live

| What | Where |
|---|---|
| Hotspot text (the six panels) | `SPOTS` near the top of the script in `index.html` |
| Brand colours (page UI) | CSS variables in `:root` at the top of `index.html` |
| Brand colours (3D room) | `const C = { … }` in the script |
| Menu board items and prices | `menuTex` (the "Menu" canvas) |
| Adoptable cats on the board | `ADOPTABLE` |
| 3D cats: coat, pose, position | the `cats` list (`pose`: `sit`, `loaf`, `sleep`, `walk`) |
| Cat coat colours | `CAT_COATS` |
| People and their speech bubbles | `CHARACTERS` |
| Wall pictures | the `photo(...)` calls, images in `wall/` |

Positions are in metres: the room is 10 × 10 m and 4 m tall, centred on `0, 0`.
`x` goes left → right, `y` is height, `z` goes from the back wall (`-5`) towards the viewer (`+5`).

## Files

- `index.html`: the whole site
- `katkafi-mascot.png`: the logo mascot
- `characters/`: the five team characters (cut-out PNGs)
- `wall/`: framed pictures on the café walls

## Notes

- Menu prices and the contact email are placeholders.
- Some wall pictures come from the internet. Check you have the rights before making this repo public or launching the site.
