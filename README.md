<div align="center">

# 👾 Mai Anh · Portfolio

**An 8-bit arcade portfolio for a chemistry competitor, STEM innovator, and community builder.**

Scroll through three "levels" — **Awards**, **Experience**, and **Leadership & Community** — and unlock every trophy, quest, and guild along the way.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla%20JS-F7DF1E?logo=javascript&logoColor=black)
![PDF.js](https://img.shields.io/badge/PDF.js-flipbook%20reader-FF2E97)
![Build step](https://img.shields.io/badge/build%20step-none-2DFF9A)
![GitHub Pages](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-181717?logo=github)

[**▶ Play the live site**](https://nglemaianh.github.io/REPO-NAME/) · [LinkedIn](https://www.linkedin.com/in/nguyenlemaianh/) · [Email](mailto:nguyenleemaianh@gmail.com)

</div>

---

<!--
## Preview

Add screenshots to a `screenshots/` folder, then remove this comment:

<p align="center">
  <img src="screenshots/home.png" alt="Hero section" width="49%">
  <img src="screenshots/awards.png" alt="Awards carousel" width="49%">
</p>
-->

## Table of contents

- [About](#about)
- [What's inside](#whats-inside)
- [Features](#features)
- [Tech stack](#tech-stack)
- [Project structure](#project-structure)
- [Getting started](#getting-started)
- [Deploying to GitHub Pages](#deploying-to-github-pages)
- [Customizing the content](#customizing-the-content)
- [Controls](#controls)
- [Troubleshooting](#troubleshooting)
- [Contact](#contact)
- [License and credits](#license-and-credits)

## About

This repository contains the personal portfolio of **Nguyen Le Mai Anh** — a Grade 12 student at **Lawrence S. Ting School** (Ho Chi Minh City, Vietnam) applying to undergraduate programmes in **Chemical Engineering** and **Chemistry**.

The site presents international and national chemistry/STEM competition results, independent research and engineering projects, and school and community leadership — wrapped in a retro-arcade theme, so browsing a portfolio feels like playing a game.

It is a **single static page**: one HTML file, no framework, no bundler, no backend. All content lives in one JavaScript object that is easy to edit.

## What's inside

| Level | Section | Content |
|:-:|---|---|
| 1 | **Awards & Honours** | 12 awards — 5 international/national (3D carousel) and 7 school achievements (trading cards; rank **S** cards get a gold holographic shine) |
| 2 | **Pre-professional Experience** | 6 "quests" — scientific research, AI, web development, hardware R&D |
| 3 | **Leadership & Community** | 8 "guilds" — clubs, student government, a founded sustainability initiative, STEM teaching, varsity sports |

**Selected highlights**

- 🥇 **1st place** — HNUE Olympic STEM 2025, out of 191 national high-school teams
- 🌏 **High Distinction (top 10% in Asia)** — International Chemistry Quiz, Royal Australian Chemical Institute
- 🥉 **Bronze Medal** — World Youth Chemistry Talent Olympiad, National Round
- 💡 **Top 10 National Finalist** — HCMUT Innovation, out of 189 projects
- 🏆 **Third Prize, twice** — Ho Chi Minh City Academic Olympiad, Chemistry (2025 and 2026)
- 🔬 **Research** — keratin-based bio-composite adsorbents (poultry feathers + kapok) for oil-spill remediation
- 🛠️ **Projects** — CHŌZ personalized-nutrition platform, Arduino flood-rescue raft, FRIDGI smart food-preservation container
- 🧪 **Leadership** — Chemyth Club (Member → Vice President → President → Advisor), House Student Commission, founder of the RE:Act sustainability project

## Features

### Arcade experience

- **Pixel sprites without image files** — invaders, ghosts, coins, hearts, stars, trophies, flasks, and joysticks are drawn from tiny text maps and rendered as inline SVG.
- **Retro atmosphere** — animated starfield, CRT scanline overlay, neon palette, and a scrolling "high-score" ticker that runs through every award.
- **Periodic-table level headers** — each level is introduced by an element tile (Au · Fe · Si) with a spectral-wavelength tag.
- **Live HUD** — SCORE and LIVES counters in the navigation bar (wide screens). Opening an award, quest, or guild for the first time unlocks **+100 points** with a toast message.
- **Hero stats that count up** — computed from the data itself, so the numbers never go out of date when you add content.
- **Interactive cards** — cards tilt toward the cursor on desktop (disabled on touch devices and for users who prefer reduced motion).
- **Easter egg** — try the Konami code: `↑ ↑ ↓ ↓ ← → ← → B A`.

### Content views

- **Awards carousel** — international and national awards sit in a 3D carousel: click a side card, use the arrow keys or dots, or swipe.
- **Trading-card grid** — school achievements as collectible cards with rank badges.
- **Quest log and guild roster** — experience as "quests" with a *CLEARED* stamp; activities as "guilds", with a *CAREER PATH* badge where a role timeline exists.
- **Detail pages** — every card opens an in-page detail view (no reload) with a cover banner, organisation logo, date or period, external links, the full story, role timeline, tags, photo gallery, and optional video. **Back** restores your scroll position, and a progress bar tracks reading progress.

### Lightbox and flipbook reader

- **Lightbox** — full-screen photo viewer with captions and a counter.
- **PDF flipbook** — research papers and project reports in `docs/` open as a page-turning book rendered in the browser with [PDF.js](https://mozilla.github.io/pdf.js/). Two-page spreads on wide screens, single pages on narrow ones, zoom (1× / 1.6× / 2.4×), full screen, a page slider, and a download link. Portrait and landscape A4 documents are both supported.

### Robust media handling

- Photos are **found by file name** (`<id>-cover`, `<id>-logo`, `<id>-1`, `<id>-2`, …) — drop them in the right folder and they appear. The loader tries `.jpg`, `.png`, `.jpeg`, `.webp`, `.JPG`, `.PNG`, and extension-less files.
- A missing image never breaks the layout — a coloured placeholder with the item's emoji is shown instead.
- Images are lazy-loaded, and gallery rows are balanced by each photo's real aspect ratio.
- Optional video (`.mp4`, `.mov`, `.webm`) on any detail page.

### Responsive and accessible

- Fluid layout with breakpoints from 1280 px down to 480 px.
- Cards and the carousel are keyboard-operable (`Enter` / `Space`) with a visible focus ring; the flipbook is a modal dialog with a focus trap.
- `prefers-reduced-motion` is respected, and hover-only effects are disabled on touch devices.
- No analytics or tracking scripts.

## Tech stack

| Layer | Details |
|---|---|
| Markup | Semantic HTML5 |
| Styling | Hand-written CSS — custom properties (design tokens), Grid, Flexbox, `clamp()`, `aspect-ratio`, keyframe animations |
| Logic | Vanilla JavaScript (ES2020+) — no framework, no build tooling |
| PDF rendering | [PDF.js](https://mozilla.github.io/pdf.js/) 5.6.205 (legacy build) from jsDelivr, with unpkg as a fallback |
| Fonts | [Google Fonts](https://fonts.google.com/) — Bungee, Press Start 2P, VT323, Be Vietnam Pro |
| Hosting | Any static host — GitHub Pages, Netlify, Vercel, Cloudflare Pages |

The site is built for modern evergreen browsers (it relies on CSS custom properties, `aspect-ratio`, dynamic `import()`, and the Fullscreen API).

## Project structure

```text
.
├── index.html          # the whole site: markup + CSS + JS + content data
├── README.md
├── docs/               # PDFs shown in the flipbook reader
│   ├── oilspill-research.pdf
│   ├── hnue-stem.pdf
│   ├── feat-week.pdf
│   ├── biology-camp.pdf
│   └── hcmut-innovation.pdf
├── images/
│   ├── profile.jpg     # hero portrait (.png / .jpeg / .webp also work)
│   ├── awards/         # <id>-cover.jpg · <id>-logo.png · <id>-1.jpg · <id>-2.jpg …
│   ├── experience/
│   └── activities/
└── screenshots/        # optional — images for this README
```

Inside `index.html`:

| Part | What it contains |
|---|---|
| `<style>` | Design tokens in `:root`, colour-theme classes (`.th-blue`, `.th-violet`, …), layout, effects, responsive rules |
| `<body>` | Navigation + HUD, hero, the three level sections (filled by JavaScript), footer, detail view, lightbox, flipbook reader |
| `<script>` → `FLIPBOOKS` | Registry of PDF documents |
| `<script>` → `const D` | **All content** — `awards`, `experience`, `activities` |
| `<script>` → the rest | Sprites, image loader, card builders, carousel, detail view, lightbox, flipbook reader, score system, easter egg |

## Getting started

> **Note:** name the main file `index.html` so GitHub Pages and most static hosts serve it at the site root.

```bash
git clone https://github.com/nglemaianh/REPO-NAME.git
cd REPO-NAME

# any static server works, for example:
python3 -m http.server 8000
# or
npx serve .
```

Then open <http://localhost:8000>.

Opening `index.html` directly mostly works, but browsers block PDF.js from reading local PDFs on `file://` pages, so the flipbook reader needs a local server.

## Deploying to GitHub Pages

1. Push the repository to GitHub (branch `main`).
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then click **Save**.
4. After a minute or two the site is live at `https://nglemaianh.github.io/REPO-NAME/`.
   Name the repository `nglemaianh.github.io` to serve it from `https://nglemaianh.github.io/` instead.

All asset paths are relative (`./images/…`, `./docs/…`), so the site works from a sub-path without changes.

## Customizing the content

### Hero and footer

Name, intended major, school, intro paragraph, e-mail, LinkedIn, and GitHub links are plain HTML in `index.html` — search for `hero-copy` and `<footer>`.

### Awards, experience, and activities

Everything else lives in `const D = { awards: [...], experience: [...], activities: [...] }`. Add an object, save, refresh — the cards, hero counters, and ticker update automatically.

<details>
<summary><b>Add an award</b></summary>

```js
{ id:'my-award',                        // also the prefix of its image files
  rank:'S',                             // optional — 'S' = gold holographic card (default 'A')
  cat:'intl',                           // 'intl' → carousel · 'school' → card grid
  panel:'p-blue', icon:'🏆',
  catLabel:'NATIONAL · FIRST PRIZE', level:'1ST PLACE', sublevel:'out of 100 teams',
  title:'Competition name',
  organization:'Organiser', year:'Dec 2026',
  summary:'One-line summary.',
  body:['First paragraph…', 'Second paragraph…'],
  tags:['National', 'STEM'],
  cardPick:[1, 2], cardLayout:'stack',   // which photos show on the card, and how
  gallery:[
    { src:'./images/awards/my-award-1.jpg', caption:'Certificate' },
    { src:'./images/awards/my-award-2.jpg' }
  ]
}
```

| Field | Purpose |
|---|---|
| `id` | Unique slug; also the file-name prefix for `<id>-cover`, `<id>-logo`, `<id>-1` … |
| `cat` | `'intl'` → "World Tour" carousel · `'school'` → "Home School" card grid |
| `rank` | Optional. `'S'` → gold card with holographic shine (default `'A'`) |
| `panel` | Colour theme: `p-blue` `p-violet` `p-amber` `p-cyan` `p-emerald` `p-indigo` `p-rose` `p-teal` `p-slate` (cycles automatically if omitted) |
| `icon` | Emoji for the card header and image placeholders |
| `catLabel`, `level`, `sublevel` | Text on the card (`level` also appears in the ticker) |
| `title`, `organization`, `year`, `summary`, `body[]`, `tags[]` | Card and detail-page text |
| `image`, `logo` | Optional explicit paths for the cover and organisation logo; `false` = none |
| `imagePos` | Optional crop for the detail banner, e.g. `'center 30%'` |
| `cardPhotos` · `cardPick` · `cardLayout` · `cardFit` | Which gallery photos appear on the card and how — see below |
| `gallery` | `[{ src, caption }]` — photos for the detail page |
| `photos` | Shortcut: exactly *N* photo slots named `<id>-1` … `<id>-N` |
| `videos` | `[{ src, caption }]` — shown large at the top of the photo column |

Card photo options: `cardPhotos: 1–4` shows the first *N* photos · `cardPick: [1, 3]` shows exactly those photo numbers · `cardLayout: 'stack'` stacks 2–3 photos vertically (best for landscape photos) · `cardFit: 'contain'` shows the whole photo instead of cropping. When photos are hidden, the card shows a "+N" badge.

</details>

<details>
<summary><b>Add an experience ("quest")</b></summary>

```js
{ id:'my-project', icon:'🧪',
  title:'Project name',
  role:'Researcher | Competition name',
  organization:'Organisation', period:'Jan – Mar 2026',
  summary:'One-line summary shown on the quest card.',
  bullets:['Achievement one…', 'Achievement two…'],
  tags:['Research', 'Chemistry'],
  links:[{ label:'Project page', url:'https://…' }],      // entries with an empty url are skipped
  flipbooks:[FLIPBOOKS.myReport],                          // optional — see "Add a PDF flipbook"
  gallery:[{ src:'./images/experience/my-project-1.jpg', caption:'Poster' }]
}
```

</details>

<details>
<summary><b>Add an activity ("guild")</b></summary>

```js
{ id:'my-club', icon:'⚗️',
  title:'Club name',
  organization:'School', period:'Jan 2024 – Present',
  topRole:'President',
  summary:'One-line summary shown on the guild card.',
  links:[{ label:'Instagram', url:'https://…' }],
  hasTimeline:true,                                        // shows the CAREER PATH badge + timeline
  timeline:[
    { period:'Jul 2025 – Jun 2026', role:'President', award:'Optional award text',
      bullets:['What I did…', 'What I achieved…'] },
    { period:'Jan – Jun 2024', role:'Member', award:null, bullets:['…'] }
  ],
  tags:['Leadership'],
  gallery:[{ src:'./images/activities/my-club-1.jpg' }]
}
```

For activities without a timeline, use `body:['Paragraph…']` instead of `hasTimeline` / `timeline`. The order of guild cards is set by the `ACT_ORDER` array near the end of the script.

</details>

<details>
<summary><b>Add photos and videos</b></summary>

Name files `<id>-cover`, `<id>-logo`, `<id>-1`, `<id>-2`, … and place them in the matching folder:

```text
images/awards/hnue-cover.jpg     ← banner on the detail page
images/awards/hnue-logo.png      ← organisation logo
images/awards/hnue-1.jpg         ← first gallery photo
images/experience/fridgi-3.png
images/activities/chemyth-12.jpg
images/profile.jpg               ← hero portrait
```

To use a different name or path, set `image:'…'` (cover) or `src:'…'` (gallery photo) explicitly. Videos are declared with `videos:[{ src:'./images/awards/my-award-1.mp4', caption:'…' }]`.

</details>

<details>
<summary><b>Add a PDF flipbook</b></summary>

1. Put the PDF in `docs/`.
2. Register it in `FLIPBOOKS` (top of the script):

   ```js
   const FLIPBOOKS = {
     // …existing entries…
     myReport: { src:'./docs/my-report.pdf', title:'My research report', orient:'portrait' }   // or 'landscape'
   };
   ```

3. Attach it to any award, experience, or activity: `flipbooks:[FLIPBOOKS.myReport]`.

The PDF is rendered page by page in the browser — no conversion needed.

</details>

### Look and feel

Colours, fonts, and sizes are CSS variables in `:root` at the top of the stylesheet. For example, `--art-ratio` sets the shape of the photo window on award cards (`297 / 210` for A4 landscape, `210 / 297` for A4 portrait).

### Editing tips

- Text fields are inserted as HTML: write `&amp;` for `&`, and `\'` for an apostrophe inside a single-quoted string.
- Compress large photos and videos before committing — it keeps the repository small and the page fast.
- GitHub Pages is **case-sensitive**: `photo.JPG` and `photo.jpg` are different files. Keep file names consistent (and free of spaces).

## Controls

| Where | Input | Action |
|---|---|---|
| Any card | `Enter` / `Space` / click | Open its detail page |
| Detail page | **Back** button | Return with scroll position restored |
| Awards carousel | `←` `→` · swipe · click a side card · dots | Rotate the carousel |
| Lightbox | `←` `→` · swipe · `Esc` | Previous / next photo · close |
| Flipbook | `←` `→` or `PgUp` `PgDn` · swipe | Turn the page |
| Flipbook | `Home` / `End` | First / last page |
| Flipbook | `+` / `-` | Zoom in / out |
| Flipbook | `Esc` | Close |
| Anywhere | `↑ ↑ ↓ ↓ ← → ← → B A` | 🎉 |

## Troubleshooting

- **A photo shows a coloured placeholder.** Check that the file name and folder match `<id>-<n>` (or the explicit `src`), that the extension is one the loader tries, and that the letter case matches exactly.
- **A document card says "PREVIEW UNAVAILABLE".** Check the path in `FLIPBOOKS`, serve the site over `http(s)` rather than `file://`, and make sure the PDF.js CDN (jsDelivr or unpkg) is reachable. The **Open PDF** button still works.
- **The page is blank or 404s on GitHub Pages.** Make sure the main file is named `index.html` and sits at the root of the published branch.

## Contact

**Nguyen Le Mai Anh** — Ho Chi Minh City, Vietnam

- ✉️ [nguyenleemaianh@gmail.com](mailto:nguyenleemaianh@gmail.com)
- 💼 [LinkedIn](https://www.linkedin.com/in/nguyenlemaianh/)
- 🐙 [GitHub](https://github.com/nglemaianh)

## License and credits

© 2026 Nguyen Le Mai Anh. All rights reserved. The text, photographs, certificates, and research documents in this repository are personal materials and may not be copied or redistributed without permission.

Third-party resources: [PDF.js](https://mozilla.github.io/pdf.js/) by Mozilla (Apache-2.0) · [Google Fonts](https://fonts.google.com/) — Bungee, Press Start 2P, VT323, and Be Vietnam Pro (SIL Open Font License).

<div align="center">

**Thanks for playing! 👾 INSERT COIN TO CONTINUE — let's talk.**

</div>
