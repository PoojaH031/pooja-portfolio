# Pooja H — Portfolio

A single-page portfolio site with a signature hero effect: your real photo is sliced into a grid of tiles that sit on top of an anime-style image. Move your cursor across it and the tiles part like scales, revealing the anime layer underneath.

## Folder structure

Keep everything exactly like this — the page won't find the images if the structure changes:

```
portfolio/
├── index.html
└── assets/
    ├── real.jpg          (your real photo)
    ├── anime.jpg          (anime-style image)
    └── certificates/       (add certificate images here later)
```

## How to run it

**Easiest way — no tools needed:**
Just double-click `index.html`. It opens straight in your browser.

**Using VS Code (optional):**
1. Extensions panel → search **"Live Server"** (by Ritwick Dey) → Install
2. File → Open Folder → select the `portfolio` folder
3. Right-click `index.html` → **Open with Live Server**
4. It opens at `localhost:5500` and auto-refreshes when you edit the file

## Editing content

Everything is in `index.html` — no build step, no dependencies. Open it in any text editor (VS Code, Notepad, etc.) and edit the text directly inside the HTML tags. Look for these sections, in order:

- `<section class="hero">` — name, tagline, tags, buttons
- `<section id="about">` — bio and the stat numbers (CGPA, projects, certifications, languages)
- `<section id="skills">` — the three skill cards
- `<section id="experience">` — the internship block
- `<section id="projects">` — the three project cards
- `<section id="certifications">` — the certificate pills
- `<section id="contact">` — email, phone, LinkedIn, GitHub links

## Adding certificate photos

1. Drop each certificate image into `assets/certificates/`
2. Send them to me (or, if you're editing by hand, wrap the relevant `<span>` in `certifications` with an `<a href="assets/certificates/yourfile.jpg" target="_blank">` tag so clicking it opens the image)

## Changing the hero photos

- Anime layer (bottom): replace `assets/anime.jpg` with a new image of the same filename, or update the path in the CSS under `.scale-base { background-image: ... }`
- Real photo layer (tiles on top): replace `assets/real.jpg`, or update the `TILE_IMAGE` constant near the bottom of `index.html`, inside the `<script>` tag

Both images should be roughly portrait-shaped (3:4) for the tiles to line up cleanly.

## Deploying it

| Platform | Steps |
|---|---|
| **GitHub Pages** | Create a repo → upload the whole `portfolio` folder contents → Settings → Pages → set source to `main` branch → live at `yourusername.github.io/reponame` |
| **Vercel** | Sign in with GitHub → New Project → import the repo → Deploy |
| **Netlify** | Drag the `portfolio` folder straight into netlify.com/drop → instant live URL |

GitHub Pages is the simplest fit since you already have `github.com/PoojaH031`.

## Notes

- No frameworks, no npm, no build tools — it's plain HTML/CSS/JS, so it'll run anywhere forever.
- The ripple effect respects `prefers-reduced-motion`, so it stays still for users who've turned off animations on their device.
