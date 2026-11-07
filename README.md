# Spider-Man: Cinematic Scroll Experience

A fan-made, scroll-driven Spider-Man site built with **HTML5, CSS3 and vanilla JavaScript**.
Animation uses **GSAP 3.12.5 + ScrollTrigger** from the cdnjs CDN. No frameworks.

## Run it locally

Open `index.html` in a browser, or serve the folder for best results:

```bash
cd spiderman-website
python3 -m http.server 8000
# visit http://localhost:8000
```

## What is inside

| File | Purpose |
| --- | --- |
| `index.html` | All markup: loader, nav, hero, intro, origin, powers, moments, villains, ending |
| `style.css` | Theme, layout, responsive rules, hover effects |
| `script.js` | Loader, GSAP timelines, ScrollTrigger scenes, web canvas, nav, cursor |
| `assets/` | Your images, videos and fonts (all optional, see below) |

## Sections and effects

- **Loader**: a web draws itself while the page loads, then the screen lifts away.
- **Hero**: letter-by-letter title, pointer-reactive web canvas, procedural city skyline, layered parallax.
- **Intro**: word reveals, clip-path image reveal with scroll zoom.
- **Origin**: pinned four-chapter story scrubbed by scroll, with a red pulse and a flash on "the bite".
- **Powers**: 3D tilt and cursor spotlight on cards; animated spider-sense rings.
- **Moments**: pinned horizontal scroll (swipeable carousel on phones).
- **Villains**: expanding panels (hover, focus, tap or keyboard).
- **Ending**: swelling red glow, closing line, back-to-top.
- Scroll progress bar, animated nav with mobile overlay menu, custom cursor (desktop only).

## VFX

- **Embers** drifting up through the hero (pauses off-screen).
- **Web-swinger flyby**: a silhouette swings across the hero on a web line every 13 seconds.
- **Web burst on every click or tap**, like a web-shot hitting a wall.
- **Title glitch**: red/cyan chromatic split every few seconds.
- **Scroll-speed warp**: headlines lean with scroll velocity (desktop).
- **Origin scene**: a spider lowers on its thread, then a shockwave, flash and screen shake on "the bite".
- **Villains**: lightning flashes light up the section when Electro is selected; animated glow, rain, sand and bolts inside the artwork.
- Anamorphic light flare, film grain, light sweeps on gallery cards, magnetic buttons.

## Assets: bundled illustrations, your photos override them

The 13 image slots ship with **original illustrations** (`assets/images/*.svg`, generated in code, so
there are no licensing issues). To use real photos, add a `.jpg` with the **same base name**
(for example `moment-1.jpg`); the site tries `.jpg` first and falls back to the `.svg`.
Videos are optional.

Image and video slots are **checked at runtime**: if no file exists, the gradient fallback stays
and no broken-image icon appears. Drop files into `assets/` using these exact names:

### Videos (`assets/videos/`, MP4 H.264, muted, under about 6 MB each, 720p is enough for mobile)

| File | Used for |
| --- | --- |
| `hero.mp4` | Full-screen hero background loop |
| `ending.mp4` | Final section background loop |

### Images (`assets/images/`, JPG or WebP renamed to `.jpg`, 1600px wide max, under 300 KB each)

| File | Used for |
| --- | --- |
| `spiderman-portrait.jpg` | Intro portrait (4:5) |
| `moment-1.jpg` to `moment-6.jpg` | Cinematic moments gallery (16:10 or 4:5) |
| `villain-goblin.jpg`, `villain-octopus.jpg`, `villain-venom.jpg`, `villain-sandman.jpg`, `villain-vulture.jpg`, `villain-electro.jpg` | Villain panels |

### Fonts

Loaded from Google Fonts: **Anton** and **Barlow** (SIL Open Font License, free for commercial use).
To self-host, download them (for example from google-webfonts-helper), put the `.woff2` files in
`assets/fonts/`, and replace the Google Fonts `<link>` in `index.html` with `@font-face` rules.

### Where to get media legally

Spider-Man artwork, film stills and trailers belong to Marvel and Sony. Use only media you own or
are licensed to use. Safe options: your own renders and photography, official press kits (check their
terms), or licensed stock footage of city rooftops, rain, night skylines and bridges.
Free stock sources: Pexels, Pixabay, Unsplash (check each file's license).

## Deploy on GitHub Pages

1. Create a new repository on GitHub (for example `spiderman-website`), set to **Public**.
2. Upload the **contents** of the folder so `index.html` is at the repository root.
   With Git:
   ```bash
   cd spiderman-website
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/spiderman-website.git
   git push -u origin main
   ```
3. In the repository, open **Settings, then Pages**.
4. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose branch `main` and folder `/ (root)`, then **Save**.
5. Wait one or two minutes. Your site will be at `https://YOUR-USERNAME.github.io/spiderman-website/`.

Tips: file names are case-sensitive on GitHub Pages, so match the names above exactly. GitHub
limits files to 100 MB, so keep videos small. Because all paths are relative, the site works in
a sub-folder URL without changes.

## Accessibility and performance

- Respects `prefers-reduced-motion`: no loader animation, no pinned scenes, no parallax; the page stays fully readable.
- Skip link, visible focus rings, keyboard-operable villain panels, labelled nav toggle.
- Videos pause when off-screen and are skipped when the browser's data-saver mode is on.
- The web canvas only animates while the hero is visible.
- If the GSAP CDN is blocked, the page falls back to a static, fully readable layout.

## Legal

Fan-made tribute. Spider-Man and related characters are trademarks of Marvel. Not affiliated with or endorsed by Marvel or Sony.
